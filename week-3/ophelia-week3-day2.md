ophelia week 3 Day 2

## Connecting Hugging Face
You'll need to log in to the HuggingFace hub if you've not done so before.

If you haven't already done so,
1. create a free HuggingFace account at https://huggingface.com
2.navigate to Settings from the user menu on the top right. Then select Access Tokens, 
3. then click the Create new token button near the top right.
4.  THEN be sure to click the button "Write" under 'Token type'.
IMPORTANT when you create your HuggingFace Access Token,
please be sure to select WRITE permissions for your key by clicking on the "Write" button, otherwise you may get problems later.
Not "fine-grained" but "Write".

In the field "Token name" you can put anything you want, like "My HF Token". This field is just for your reference.

Then press "Create token" and then copy it into your clipboard, and keep a record of your token! It should start "hf_..."

Back here in colab, press the "key" icon on the side panel to the left, and add a new secret:
In the name field put HF_TOKEN
In the value field put your actual access token: hf_...
Ensure the notebook access switch is turned ON.

Execute the cell below to log in. You'll need to do this on each of your colabs. 
It's a really useful way to manage your secrets without needing to type them into colab.

## code
from huggingface_hub import login
from google.colab import userdata

hf_token = userdata.get('HF_TOKEN')
login(hf_token, add_to_git_credential=True)


