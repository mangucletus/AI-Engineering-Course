# Cletus: Week 1, Day 4

- Date: [YYYY-MM-DD]
- Topic: transformers, parameters, tokens, memory, context window, costs
- Notebook: week1/day4.ipynb

## Key concepts
- Transformer (2017, "Attention Is All You Need"): attention looks at all the words at once, so training scales.
- Parameters = model size. GPT-3 175B, Llama 3.1 405B, DeepSeek V3 671B.
- Token: about 4 characters, or 3/4 of a word. 1,000 tokens is roughly 750 words.
- Each model family has its own tokenizer (tiktoken for OpenAI).
- API calls are stateless. "Memory" is just resending the whole conversation every call.
- Context window: max tokens per call (prompt + history + reply).
- Cost is per token, output costs more than input. Long chats cost more every turn.

## Code / examples
Tokens:
```python
import tiktoken

enc = tiktoken.encoding_for_model("gpt-4.1-mini")
tokens = enc.encode("Hi my name is Ed and I like banoffee pie")
print(len(tokens), [enc.decode([t]) for t in tokens])
```

Chatbot with memory (save as chatbot.py in week1):
```python
from dotenv import load_dotenv
from openai import OpenAI

load_dotenv(override=True)
openai = OpenAI()
messages = [{"role": "system", "content": "You are a helpful assistant"}]

while (user := input("You: ")) != "quit":
    messages.append({"role": "user", "content": user})
    response = openai.chat.completions.create(model="gpt-4.1-nano", messages=messages)
    reply = response.choices[0].message.content
    messages.append({"role": "assistant", "content": reply})
    print("AI:", reply)
```

Run it (same on both):
```bash
uv run chatbot.py
```

## Exercise / challenge
- Tell the bot your name, then ask for it. Then remove the appends and try again: it forgets.
- Tokenize your name and a sentence in another language.

## Questions & blockers
- Models struggle to count letters because they see tokens.

## To discuss with my partner
- How do we keep a long chat cheap? (summarize old turns, keep the last few)

## Resources
- https://platform.openai.com/tokenizer
