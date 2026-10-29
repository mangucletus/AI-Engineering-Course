 Ophelia: Week 1, Day 4

- Date: 2026-10-29
- Topic: Transformers, GPT, tokens, memory, context window, new jobs
- Notebook: week1/day4.ipynb

Key concepts

- GPT means Generative Pre-trained Transformer.
- 2017: Scientists published "Attention Is All You Need" paper. Proposed Transformer architecture.
- Before Transformer we had LSTMs (Long Short Term Memory). Problem: hard to parallelize, time consuming, process word by word step by step.
- Transformer: Looks at all words at once (attention), good at math, fully parallelized. That's why LLMs could scale.
- Parameters = model size. GPT-3 175B, Llama 3.1 405B, DeepSeek V3 671B.
- Token: Small chunk. ~4 chars or 3/4 word. 1000 tokens ≈ 750 words. Each model family has own tokenizer (tiktoken for OpenAI).
- API is stateless. No memory. "Memory" is just our code resending full chat history every call.
- Context window = max tokens per call (prompt + history + reply). Long chat fails when full.
- Cost is per token. Output costs more than input. Long chats cost more.

- Evolution of jobs:
    1. Prompt Engineers - rise and fall (just prompting not enough now)
    2. Co-pilots - still active (like GitHub Copilot helping code)
    3. Context Engineers - new role, thinking broadly about what input to give LLM to make better output
    4. Agentic AI - letting model decide what to do next by itself.

Code / examples

```python
import tiktoken
enc = tiktoken.encoding_for_model("gpt-4.1-mini")
tokens = enc.encode("Hi my name is Ophelia and I like jollof")
print(len(tokens), [enc.decode(t) for t in tokens])
