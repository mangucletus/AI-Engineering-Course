 Ophelia: Week 2, Day 1 

 Calling Frontier Models (Anthropic, Google)

- OpenRouter gives you access to multiple models (websites).
    - e.g. OpenAI, Anthropic, Gemini, Google

- After paying bill, save your API key in your .env file

- You can connect to any model (provider) model using the OpenAI client library

Code

```python
openai = OpenAI() # Create Python Client Library

tell_a_joke = [
    {"role": "user", "content": "tell a joke for a student on the journey to becoming an LLM Engineering"},
]

response = openai.chat.completions.create(model="gpt-4.1-mini", messages=tell_a_joke)
display(Markdown(response.choices[0].message.content))

NotesSmall model, low reasoning effort = wrong Answer
Big Model, minimal/low reasoning effort = Right Answer
Smaller Model, minimal reasoning effort = Right Answer
Routers and Abstraction layers - help connect to all different models.

 Prompt Caching
- Prompt Caching is a great way to reduce your input Context
- If you are dealing with a big data

Types
- Implicit prompt caching
- Explicit prompt caching

 Code
```python
def call_gpt():
    messages = [{"role": "system", "content": gpt_system}]

    for gpt, claude in zip(gpt_messages, claude_messages):
        messages.append({"role": "user", "content": gpt})
        messages.append({"role": "assistant", "content": claude_messages})

    messages.append({"role": "user", "content": gpt_messages[-1]})

    response = anthropic.chat.completions.create(model=claude_model, messages=messages)
    return response.choices[0].message.content
