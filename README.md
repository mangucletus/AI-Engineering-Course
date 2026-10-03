# AI-Engineering-Course

**LLM Engineering: Master AI and Large Language Models** (Ed Donner) together.
[Udemy](https://www.udemy.com/course/llm-engineering-master-ai-and-large-language-models/) · [Course repo](https://github.com/ed-donner/llm_engineering) · [Resources](https://edwarddonner.com/2024/11/13/llm-engineering-resources/)

## Structure

- 8 sections = 8 weeks, 5 days each → `section-1/` … `section-8/`
- Each folder has a note for each of us per day, plus a shared weekly summary (each as `.md` + `.pdf`):

```
section-1/
├── cletus-section1-day1.md/.pdf … day5
├── ophelia-section1-day1.md/.pdf … day5
└── summary.md/.pdf
```

The files are already created with `[placeholders]`. Replace them with your own notes.

## Daily routine

1. `git pull`
2. Do the day's lectures and lab (`weekN/dayD.ipynb` in your own clone of the course repo).
3. Fill in your note for the day. Keep it short, in your own words.
4. Export the PDF (VS Code *Markdown PDF* extension → right-click → Export (pdf)).
5. Push:
   ```bash
   git add section-1/cletus-section1-day1.*
   git commit -m "cletus: section 1 day 1 notes"
   git pull --rebase && git push
   ```
6. Read your partner's note and comment on GitHub.

After Day 5, fill in `summary.md` together at the weekly meeting and export its PDF.

## Rules

- Only edit your own notes. `summary.md` is shared, so write it together.
- Never commit API keys or `.env` files.
- Use cheap or free models (`gpt-4.1-nano`, Ollama) to keep costs low.

## Working together

- Same week and day as each other.
- 15-30 min daily check-in: what I did, what's unclear, what's blocking me.
- Pair on the big labs (Week 2, Week 5, Weeks 6–8).
- Weekly meeting (1 hr, Friday or weekend): review the week, write the summary together, agree on next week's pace.
- If you fall behind, say so early.
