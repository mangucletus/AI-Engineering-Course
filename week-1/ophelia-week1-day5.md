 Ophelia: Week 1, Day 5

- Date: 2026-10-29
- Topic: Brochure generator, JSON output, chaining calls, streaming
- Notebook: week1/day5.ipynb, week1/week1_EXERCISE.ipynb

 Key concepts

- Chaining: Use 2 LLM calls. Call 1 picks the relevant links from a website (returns JSON). Call 2 takes those pages and writes the brochure. This is my first taste of agents.
- One-shot prompting: In the prompt, show one example of the exact output you want, so model copies the format.
- JSON mode: If I want structured output, I must do 2 things: 1) say "Reply in JSON" in the prompt, 2) add response_format={"type": "json_object"}. Then use json.loads() to parse.
- Streaming: Instead of waiting for full reply, get it word by word with stream=True. Read chunk.choices[0].delta.content.
- System prompt sets the tone (funny, professional, etc).
- Truncate long website text before sending to save tokens and fit context window.

Code 

1. Get links as JSON (Call 1):
```python
import json
from dotenv import load_dotenv
from openai import OpenAI

load_dotenv(override=True)
openai = OpenAI()

system = 'Reply in JSON like {"links": [{"type": "about page", "url": "https://..."}]}'
user = "Pick the About and Careers links: /about, /careers, /privacy, /blog"

response = openai.chat.completions.create(
    model="gpt-4.1-nano",
    messages=[{"role": "system", "content": system}, {"role": "user", "content": user}],
    response_format={"type": "json_object"}
)

print(json.loads(response.choices[0].message.content))
