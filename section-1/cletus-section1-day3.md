# Cletus — Section 1, Day 3

- **Date:** [YYYY-MM-DD]
- **Course:** Week 1, Day 3 — Types of LLM, frontier models' strengths and pitfalls, agentic AI
- **Lab notebook:** none (lecture day, practised in chat apps)
- **Time spent:** [e.g. 1h]

## Key concepts
- **Base model** — trained on huge amounts of text to predict the next token. It continues text but doesn't follow instructions well.
- **Chat (instruct) model** — a base model fine-tuned on conversations and human feedback (RLHF) so it follows instructions and chats. ChatGPT uses this kind of model.
- **Reasoning model** — trained to "think" step by step before answering, using hidden thinking tokens. Better at maths, logic and code, but slower and costs more. Examples: GPT-5 Thinking, DeepSeek R1.
- **The frontier models** — GPT (OpenAI), Claude (Anthropic), Gemini (Google), Grok (xAI), plus DeepSeek (open-weight).
- **Strengths** — summarizing and combining information, turning an outline into a full draft, writing and explaining code.
- **Pitfalls:**
  - *Knowledge cutoff:* they don't know recent events unless they can search the web.
  - *Niche or specialized topics:* answers can be shallow or wrong.
  - *Hallucinations:* they can be confidently wrong.
  - *Token quirks:* they see tokens, not letters, so counting letters is hard for them.
- **Agentic AI** — the model plans and takes several steps using tools:
  - *Deep Research* searches the web and writes a report.
  - *Claude Code* writes and runs code in your terminal.
  - *Agent Mode* in ChatGPT uses a browser to complete tasks.
- **LLM competition game** — models play against each other, which shows how differently they behave. It also previews several LLMs talking to each other (Week 2).

## Code / examples
No code today. Test prompts to compare models:

| Test | Prompt | What it shows |
|---|---|---|
| Token quirk | How many times does the letter "r" appear in "strawberry"? | Models see tokens, not letters |
| Knowledge cutoff | What were the biggest AI announcements this week? | Cutoff vs web search |
| Reasoning | A short logic puzzle or riddle | Chat vs reasoning model |
| Hallucination | Summarize the paper "[made-up title]" by [made-up author] | Does it invent an answer or admit it doesn't know? |

## Exercise / challenge
1. Run the 4 prompts above in 2–3 free chat apps (ChatGPT, Claude, Gemini, DeepSeek).
2. Turn "thinking" or "reasoning" on and off where the app allows it, and compare.
3. Note in a small table which model was right, fastest and clearest.

## Questions & blockers
Watch out for:
- Don't trust answers about recent events or niche facts without checking them.
- A better model isn't always the right choice: reasoning models cost more and are slower.

## To discuss with my partner
- Which model won on which prompt? Did we get the same results?
- When is a reasoning model worth the extra time and cost?

## Resources
- ChatGPT: https://chatgpt.com · Claude: https://claude.ai · Gemini: https://gemini.google.com · DeepSeek: https://chat.deepseek.com
- Compare models on a leaderboard: https://lmarena.ai
