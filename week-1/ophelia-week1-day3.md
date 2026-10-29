 Ophelia: Week 1, Day 3

- Date: 2026-10-29
- Topic: LLM comes in 3 flavors (breeds), Frontier Models, What frontier can do
- Notebook: week1/day3.ipynb

 Key concepts

LLM comes in 3 flavors:

 Base Models:
- The original model. Takes sequence of inputs and predicts what comes next.
- Example: predictive text on phone keyboard. Good for fine-tuning to learn a new skill.
- ChatGPT came out in 2022 from this.

Chat / Instruct Models:
- A base model trained with more data to work in prompt style.
- Structure: System prompt (role) + User prompt (task) -> Assistant reply.
- Better for interactive use cases, creative work, and content generation.
- Example: ChatGPT, Claude, Gemini.

 Reasoning / Thinking Models:
- Trained to think methodologically, step-by-step before answering.
- First outputs its thinking steps (Chain of Thought), then gives final answer.
- Better for problem solving, math, coding. But uses more tokens = budget forcing.
- Example: GPT-5, Gemini Pro 2.5 are Hybrid models (they can be chat + reasoning).
- The "Wait" word discovery: Making model pause and rethink makes answer more efficient. That's frontier trick.

Frontier Models - the big companies:
- OpenAI: GPT models, ChatGPT
- Anthropic: Claude
- Google: Gemini, Gemma
- x.ai: Grok
- DeepSeek AI: DeepSeek

Mind-blowing performance from Frontier LLMs:

1. Synthesizing information: Answer a question in depth with well-researched, structured answer, often with summary.
2. Fleshing out a skeleton: From a couple notes, build a well-crafted email or blog post and keep iterating until perfect.
3. Coding: Write and debug code. Has overtaken Stack Overflow as #1 resource for engineers.

 Questions & blockers

- Base model vs Chat model confused me before, now clear: Base = next word predictor, best for fine tuning to learn a skill Chat = trained to follow instructions, best for interactions and creative content 
- Reasoning models cost more because they think before answering.

 Resources

- Udemy: LLM Engineering - Week 3 Day 1
