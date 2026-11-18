 Ophelia: Week 8, Day 1

## Projects To Be Built

1. Scanner Agent - Identifies promising deals
2. Ensemble Agent - Estimates prices using multiple models
3. Messaging Agent - Sends push notifications
4. Planning Agent - Coordinates activities
5. The Agent Framework - With memory and logging
6. The UI - In Gradio, naturally

## Frameworks For Building Agentic Setups

1. Crew AI
2. OpenAI Agents
3. S-T-K
4. ADK (Google)

They are responsible for:

1. Tools identification
2. LLMs calling
3. Handling observability

Anthropic recommend that when building simpler Agents, mostly achieved without using Agent Frameworks because it can be done by just calling LLMs and it deepens your understanding about how it actually works

## Building Can Be Done By

1. Calling LLMs
2. Using Tools

### Modal.com - Useful For Running Inference

Advantages:
Modal is easy to set up and configure
Modal is less expensive - charges as you use
Modal makes it easy to write python code which can be run locally on your computer or on the cloud

```python
reply = hello.local() - runs locally
reply = hello.remote() - runs remotely
