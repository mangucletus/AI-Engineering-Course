# Ophelia: Week 8, Day 3

Scanner Agent, Messaging Agent
### Structured Outputs

#### How It Feels

You define a Python class as a subclass of Pydantic BaseModel

1. The model outputs an instance of this class

#### How It Works

The Pydantic class is used to generate a JSON Schema

- OpenAI includes the schema in the system prompt:
"You must respond with JSON according to this schema"
- OpenAI client library creates an instance of the Pydantic class and populates with the JSON

And there's a powerful trick - Inference-time Constrained decoding

### Pushover

Pushover is a nifty tool for sending Notifications to your phone
It is super easy to set up and install.
Simply visit "https://pushover.net/" and click "Login or Sign up" to create an Account and Create an API keys.
