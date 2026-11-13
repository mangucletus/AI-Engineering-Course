 Ophelia: Week 7, Day 2

## To Sign Up and Create a Token

To sign up and create a token
Visit https://huggingface.com

Select the secrets for this Notebook by clicking on the key icon in the left, and add a new secret called "HF_TOKEN" with the value as your token

## Log In to Hugging Face

```python
hf_token = userdata.get('HF_TOKEN')
login(hf_token, add_to_git_credential = True)

## Load our Data
dataset = load_dataset(DATASET_NAME)
train = dataset['train']
val = dataset['val']
test = dataset['test']
test[0]

Prepare Our Base Llama Model for Evaluation
Trying out our base Llama 3.1 model against the Test dataset
evaluate(model_predict, test)
