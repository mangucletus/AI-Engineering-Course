ophelia Week 3 Day 1
Welcome to Google Colab - using free and powerful compute in the cloud.

Google Colab gives you a remote Notebook-style browser window on to a machine, and you run code "locally" on that machine.

Benefits of Colab
Free access to T4 GPUs!
Easy ability to share code and collaborate on it
Everyone gets to use identical code - no environment differences
Downsides of Colab
As it's free, Google reserves the right to bump you off the box at any point ("reset the runtime"), and this happens most quickly if no code is running. They can also downgrade you from a T4 to a CPU-only box. Sometimes this happens silently. You need to start everything again from the top. Paid plans last longer.
You need to pip install packages every single time (but no pip installs today)
There's some latency - it's not as interactive as coding on your own box
Survival Guide
Always start by pressing the drop down arrow by Connect on the top right, and "Connect to a hosted runtime: T4"
From that dropdown, "View Resources" to check you have a GPU and monitor memory
If things go awry, Runtime >> Disconnect and Delete Runtime, Connect again, and then run cells from the top
Always run the pip installs! Ignore pip dependency errors.
Runtime >> Restart session: this restarts the Python Kernel, but pip packages remain installed and the disk remains the same.

Runtime >> Disconnect and delete session. This wipes everything.
 I've had to add in this pip install since making the video, as HuggingFace made a breaking change!

!pip install -q --upgrade transformers==4.56.2 diffusers==0.32.2
# Let's check the GPU - it should be a Tesla T4

gpu_info = !nvidia-smi
gpu_info = '\n'.join(gpu_info)
if gpu_info.find('failed') >= 0:
  print('Not connected to a GPU')
else:
  print(gpu_info)
  if gpu_info.find('Tesla T4') >= 0:
    print("Success - Connected to a T4")
  else:
    print("NOT CONNECTED TO A T4")
