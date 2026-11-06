 Gradio, the remarkable platform for data science UIs

- Create a simple UI using Gradio
- Hook up Gradio to a frontier Model LLM

What is Gradio?

- Gradio is an python open source python library owned by the company that created Hugging Face and it allows you to write a python code that generates a UI.

 Code

import gradio as gr

def greet(name):
    return "Hello " + name + "!"

demo = gr.Interface(fn=greet, inputs="text", outputs="text")
demo.launch()

 
 Notes

- Responses API locked in OpenAI ecosystem - not common to other providers.
- Chat Completions API allows access to other providers

Gradio's Share Tool

Use Gradio's Share tool - By adding share="True" to your code.
 Gradio sends your code to Gradio / Hugging Face to be hosted and shared with others and every response is brought to your machine through http tunneling

- Markdown response change response from simple text

- Stream - gpt(prompt): stream responses
  Exercises

1. Create a UI for API calls to Frontier Models
2. Create a UI for the Company Brochure from Week 1
3. Include streaming and Markdown
