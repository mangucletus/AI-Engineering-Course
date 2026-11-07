Ophelia: Week 2, Day 5 - Agentic AI

# Agentic AI

- Agents are defined as LLMs that control the workflow
- LLM agent runs tools in a loop to achieve a goal

# Common features

- Memory / persistence
- Planning capabilities
- Autonomy
- LLM orchestration via Tools

# Notes

- The root calls the python function called "chat"
# A bit more about what Gradio actually does:

1. Gradio constructs a frontend Svelte app based on our Python description of the UI
2. Gradio starts a server built upon the Starlette web framework listening on a free port that serves this Svelte app
3. Gradio creates backend routes for our callbacks, like chat(), which calls our functions

And of course when Gradio generates the frontend app, it ensures that the the Submit button calls the right backend route.

