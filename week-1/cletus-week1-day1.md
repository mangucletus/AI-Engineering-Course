# Cletus: Week 1, Day 1

- Date: 2026-10-05 (Monday)
- Topic: first local LLM with Ollama, setup, website summarizer
- Notebook: week1/day1.ipynb

## Key concepts
- LLM: predicts the next token from the text so far.
- Ollama: runs open-source models locally for free. llama3.2 is fine (llama3.2:1b on a weak laptop). Not llama3.3, too big.
- Frontier models: GPT, Claude, Gemini. Closed, used through a paid API.
- System prompt: the model's job and tone. User prompt: the actual request.
- Messages: a list of {"role": ..., "content": ...} dicts.
- The reply is in response.choices[0].message.content.
- API key lives in .env. Never commit it.

## Code / examples
Setup (once).

Linux (Ubuntu):
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
curl -fsSL https://ollama.com/install.sh | sh
```

Windows (PowerShell):
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
winget install --id Ollama.Ollama -e
```

Then in a new terminal (same on both):
```bash
git clone https://github.com/ed-donner/llm_engineering.git
cd llm_engineering
uv sync
ollama run llama3.2
```

Create a file called .env in llm_engineering with:
```text
OPENAI_API_KEY=sk-proj-your-key-here
```

Website summarizer (notebook cell in week1):
```python
from dotenv import load_dotenv
from openai import OpenAI
from scraper import fetch_website_contents

load_dotenv(override=True)
openai = OpenAI()

def summarize(url):
    messages = [
        {"role": "system", "content": "Summarize this website in markdown."},
        {"role": "user", "content": fetch_website_contents(url)},
    ]
    response = openai.chat.completions.create(model="gpt-4.1-mini", messages=messages)
    return response.choices[0].message.content

print(summarize("https://edwarddonner.com"))
```

## Exercise / challenge
- Change the system prompt tone (Spanish, formal, funny) and compare.
- Summarize an email instead: paste it in as the user prompt.

## Questions & blockers
- JS-heavy sites like openai.com come back nearly empty. The scraper only reads raw HTML.
- NameError: run cells from the top and check the .venv kernel.

## Resources
- https://github.com/ed-donner/llm_engineering/tree/main/week1
