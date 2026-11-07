 Ophelia: Week 2, Day 3

 Prompting

 One Shot prompting
- Giving one question and answer to the model for it to replicate.

 Multi Shot prompting
- Giving the model more examples on how to respond in different situations.

Code

def chat(message, history):
    relevant_system_message = system_message

    if "belt" in message.lower():
        relevant_system_message += " The store does not sell belts. If you are asked for belts, be sure to point out other items on sale"

    messages = [{"role": "system", "content": relevant_system_message}] + history + [{"role": "user", "content": message}]

    stream = openai.chat.completions.create(model=MODEL, messages=messages, stream=True)

    response = ""
    for chunk in stream:
        response += chunk.choices[0].delta.content or ""
        yield response

 Callback Function

def chat(message, history):
    # These functions take a message,
    # take the prior conversation and
    # return the response

    gr.ChatInterface(fn=chat, type="messages", launch())

    history = [{"role": h["role"], "content": h["content"]} for h in history]

 Notes

- Makes no difference in OpenAI but a whole lot of work in Gemini
