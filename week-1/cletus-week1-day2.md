# Cletus: Week 1, Day 2

- Date: 2026-10-06 (Tuesday)
- Topic: frontier vs open-source models, Chat Completions API, OpenAI-compatible endpoints
- Notebook: week1/day2.ipynb

## Key concepts
- Frontier (closed): GPT, Claude, Gemini, Grok. Open-source: Llama, Mistral, DeepSeek, Qwen, Gemma.
- Chat Completions API: send a conversation, get the next message back. Most providers copy OpenAI's format.
- The openai package is just a wrapper around an HTTP POST. No model inside it.
- Same client works for other providers, only base_url and api_key change.
- Distillation: a small model trained to copy a big one (deepseek-r1:1.5b).
- Local models: free and private, but weaker.

## Code / examples
Same client, different providers:
```python
import os
from dotenv import load_dotenv
from openai import OpenAI

load_dotenv(override=True)

ollama = OpenAI(base_url="http://localhost:11434/v1", api_key="ollama")
gemini = OpenAI(base_url="https://generativelanguage.googleapis.com/v1beta/openai/",
                api_key=os.getenv("GOOGLE_API_KEY"))

messages = [{"role": "user", "content": "Tell me a fun fact"}]
response = ollama.chat.completions.create(model="llama3.2", messages=messages)
print(response.choices[0].message.content)
```

Check Ollama is running.

Linux (Ubuntu):
```bash
curl http://localhost:11434
```

Windows (PowerShell):
```powershell
curl.exe http://localhost:11434
```

Download a model (same on both):
```bash
ollama pull llama3.2
```

## Exercise / challenge
- Switch the Day 1 summarizer to Ollama (change the client and model) and compare with GPT.

## Questions & blockers
- llama3.3 and llama4 are too big for a laptop.
- After editing .env, reload it with load_dotenv(override=True).

## Resources
- guides/09_ai_apis_and_ollama.ipynb in the course repo
