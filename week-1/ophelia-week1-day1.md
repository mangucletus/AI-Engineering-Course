  Ophelia: Week 1, Day 1

- Date: 2026-10-29
- Topic: First local LLM with Ollama, environment setup, website summarizer project
- Notebook: week1/day1.ipynb

  Key concepts
- Ollama: a tool that lets me run open-source LLMs on my own laptop for free, without paying API.
- Frontier models: GPT-4o, Claude, Gemini - these are very powerful but closed. We can only use them by calling their API and paying.
- System prompt = I tell the model who it is and how to behave. Example: "You are a helpful assistant that summarizes websites."
- User prompt = the real task I want it to do. Example: "Summarize this website..."
- Security: My API key must be in a .env file. I must never push .env to GitHub. Add .env to .gitignore.

**Setup - do once (Ubuntu / WSL):
```bash
# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Pull and run a small model
ollama run llama3.2

# Install Python packages
pip install openai python-dotenv requests beautifulsoup4
