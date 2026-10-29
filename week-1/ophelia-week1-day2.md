# Ophelia: Week 1, Day 2

- Date: 2026-10-29
- Topic: Frontier vs open-source models, Chat Completions API, using OpenAI client for everything
- Notebook: week1/day2.ipynb

## Key concepts

- The simplest way to call an LLM is called Chat Completions
- It says: "here is a conversation, please predict what should come next"
- The Chat Completions API was invented by OpenAI, but it's so popular that everybody uses it!
- The `openai` Python package is NOT a model. It's just a helper that makes an HTTP request for you.
- Because everyone copies OpenAI's format, the same code works for Ollama, Gemini, Groq, etc. Just change base_url and api_key.
- Distillation: Training a small model (like deepseek-r1:1.5b) to behave like a big model, so it becomes smarter but still small.
- Local models are private and free, but their answers are weaker than frontier models.

## Code / examples
import os
from dotenv import load_dotenv

load_dotenv(override=True)
api_key = os.getenv('OPENAI_API_KEY')

if not api_key:
    print("No API key was found - please head over to the troubleshooting notebook in this folder to identify & fix!")
elif not api_key.startswith("sk-proj-"):
    print("An API key was found, but it doesn't start sk-proj-; please check you're using the right key - see troubleshooting notebook")
else:
    print("API key found and looks good so far!")
This code verifies if your API key can be found
