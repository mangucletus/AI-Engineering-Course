ophelia week3- Day 4 
## Models
Looking at the lower level API of Transformers - the models that wrap PyTorch code for the transformers themselves.

This notebook can run on a low-cost or free T4 runtime.

[ ]
!pip install -q --upgrade bitsandbytes accelerate transformers==4.57.6

[ ]
from google.colab import userdata
from huggingface_hub import login
from transformers import AutoTokenizer, AutoModelForCausalLM, TextStreamer, BitsAndBytesConfig
import torch
import gc
Sign in to Hugging Face
If you haven't already done so, create a free HuggingFace account at https://huggingface.co and navigate to Settings,
then Create a new API token, giving yourself write permissions by clicking on the WRITE tab

Press the "key" icon on the side panel to the left, and add a new secret: HF_TOKEN = your_token

Execute the cell below to log in.


[ ]
hf_token = userdata.get('HF_TOKEN')
login(hf_token, add_to_git_credential=True)
Accessing Llama
Yesterday you should have received approval to use this model:

https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct

You can either use that today, or it's faster if you get approval for this model too.

https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct

Select this link to see if you need to request approval too. Pick the version of Llama that you want below by commenting out one of these! 
Or skip Llama altogether.


[ ]
# instruct models and 1 reasoning model

# Llama 3.1 is larger and you should already be approved
# see here: https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-Instruct

# LLAMA = "meta-llama/Meta-Llama-3.1-8B-Instruct"

# Llama 3.2 is smaller but you might need to request access again
# see here: https://huggingface.co/meta-llama/Llama-3.2-1B-Instruct

LLAMA = "meta-llama/Llama-3.2-1B-Instruct"

PHI = "microsoft/Phi-4-mini-instruct"
GEMMA = "google/gemma-3-270m-it"
QWEN = "Qwen/Qwen3-4B-Instruct-2507"
DEEPSEEK = "deepseek-ai/DeepSeek-R1-Distill-Qwen-1.5B"
Accessing Llama 3.1 from Meta
In order to use the fantastic Llama 3.1, Meta does require you to sign their terms of service.

Visit their model instructions page in Hugging Face: https://huggingface.co/meta-llama/Meta-Llama-3.1-8B


# Quantization Config - this allows us to load the model into memory and use less memory

quant_config = BitsAndBytesConfig(
    load_in_4bit=True,
    bnb_4bit_use_double_quant=True,
    bnb_4bit_compute_dtype=torch.bfloat16,
    bnb_4bit_quant_type="nf4"
)

# Tokenizer

tokenizer = AutoTokenizer.from_pretrained(LLAMA)
tokenizer.pad_token = tokenizer.eos_token
inputs = tokenizer.apply_chat_template(messages, return_tensors="pt").to("cuda")

[ ]
inputs

[ ]
# The model

model = AutoModelForCausalLM.from_pretrained(LLAMA, device_map="auto", quantization_config=quant_config)

[ ]
memory = model.get_memory_footprint() / 1e6
print(f"Memory footprint: {memory:,.1f} MB")
Looking under the hood at the Transformer model
The next cell prints the HuggingFace model object for Llama.

This model object is a Neural Network, implemented with the Python framework PyTorch.
The Neural Network uses the architecture invented by Google scientists in 2017: the Transformer architecture.


There's something called "embedding" - this takes tokens and turns them into 4,096 dimensional vectors. 
There are then 16 sets of groups of layers (32 for Llama 3.1) called "Decoder layers". 
Each Decoder layer contains three types of layer: (a) self-attention layers (b) multi-layer perceptron (MLP) layers (c) batch norm layers.
There is an LM Head layer at the end; this produces the output






