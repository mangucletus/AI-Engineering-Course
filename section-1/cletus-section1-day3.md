# Cletus: Section 1, Day 3

- Date: [YYYY-MM-DD]
- Course: Week 1 Day 3, types of LLMs, what frontier models are good and bad at, and agentic AI
- Lab notebook: none, this was a lecture day. Practice was done in the chat apps.
- Time spent: [e.g. 1h]

## Key concepts
- Base model: trained on a huge amount of text to predict the next token. It continues text but isn't good at following instructions.
- Chat (instruct) model: a base model that was fine-tuned on conversations and human feedback (RLHF) so it follows instructions. ChatGPT is built on this kind of model.
- Reasoning model: trained to think through a problem step by step before answering, using hidden "thinking" tokens. Better at maths, logic and code, but slower and more expensive. GPT-5 Thinking and DeepSeek R1 are examples.
- Main frontier models: GPT (OpenAI), Claude (Anthropic), Gemini (Google), Grok (xAI), plus DeepSeek, which is open-weight.
- What they're good at: summarizing and combining information, turning an outline into a full draft, and writing and explaining code.
- Where they fall down:
  - Knowledge cutoff, so they don't know recent events unless they can search the web.
  - Niche or specialized topics, where answers can be shallow or wrong.
  - Hallucinations, where they sound confident but are wrong.
  - Counting letters, since they see tokens and not letters.
- Agentic AI: the model makes a plan and carries it out over several steps using tools. Deep Research searches the web and writes a report, Claude Code writes and runs code in the terminal, and ChatGPT's Agent Mode uses a browser to get things done.
- LLM competition game: models play a game against each other, which shows how differently they behave. It's also a preview of getting several LLMs to talk to each other in Week 2.

## Code / examples
No code today. These prompts are good for comparing models:

| Test | Prompt | What it shows |
|---|---|---|
| Letters vs tokens | How many times does the letter "r" appear in "strawberry"? | Models see tokens, not letters |
| Knowledge cutoff | What were the biggest AI announcements this week? | Cutoff vs web search |
| Reasoning | A short logic puzzle or riddle | Chat model vs reasoning model |
| Hallucination | Summarize the paper "[made-up title]" by [made-up author] | Whether it invents an answer or admits it doesn't know |

## Exercise / challenge
1. Run the 4 prompts above in 2 or 3 free chat apps (ChatGPT, Claude, Gemini, DeepSeek).
2. Where the app lets you, turn thinking/reasoning on and off and compare.
3. Keep a small table of which model was right, which was fastest and which explained it best.

## Questions & blockers
Things to watch out for:
- Don't trust answers about recent events or niche facts without checking them.
- The strongest model isn't always the right pick. Reasoning models are slower and cost more.

## To discuss with my partner
- Which model did best on which prompt? Did we get the same results?
- When is a reasoning model worth the extra time and cost?

## Resources
- ChatGPT: https://chatgpt.com
- Claude: https://claude.ai
- Gemini: https://gemini.google.com
- DeepSeek: https://chat.deepseek.com
- Leaderboard for comparing models: https://lmarena.ai
