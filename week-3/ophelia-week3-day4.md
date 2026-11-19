# Ophelia: Week 3, Day 4 - Models

## What We Are Doing Today

Today we look at the lower level API of Transformers.
These are the models that wrap PyTorch code for the Transformers themselves.

This notebook can run on a low-cost or free T4 runtime.

 Install The Libraries

```python
!pip install -q --upgrade bitsandbytes accelerate transformers==4.57.6

from google.colab import userdata
from huggingface_hub import login
from transformers import AutoTokenizer, AutoModelForCausalLM, TextStreamer, BitsAndBytesConfig
import torch
import gc

 Sign In To Hugging FaceIf you haven't already,
create a free Hugging Face account at https://huggingface.coGo to Settings
Create a new API token,
giving yourself Write permissions by clicking on the WRITE tabPress the "key" icon on the side panel to the leftAdd a new secret: HF_TOKEN = your_tokenThen
run this cell to log in:
hf_token = userdata.get('HF_TOKEN')
login(hf_token, add_to_git_credential=True)

 Accessing Llama, you should have received approval to use this model:https://huggingface.co/meta-llama/Meta-Llama-3.1-8B-
InstructYou can either use that today,
 or it's faster if you get approval for this model too:https://huggingface.co/meta-llama/Llama-3.2-1B-
InstructPick the version of Llama that you want below by commenting out one of these. Or skip Llama altogether

