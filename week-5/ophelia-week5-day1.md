 Ophelia: Week 5, Day 1 - RAG

# Objectives

1. Big idea behind RAG.
2. Walk through the high level flow for adding expertise to queries
3. Implement a toy version of RAG without vector databases.

# Getting Models To Answer More Accurately

In order to get models to answer more accurately and appropriately, we might use

1. Multi-shot prompting
2. Tools
3. Additional Context

We can also take it to the next level by:

- Building a database of expert information, called a Knowledge Base
- Everytime, Everytime a user asks a question, it search for anything relevant in the Knowledge Base
- Add relevant details to the prompt

The Small Idea Behind RAG

Improve the prompt with content from a knowledge base

# Flow

Chat -- Question --> Code -- Prompt --> LLM
Chat <-- Answer -- Code <-- Response -- LLM
Code -- Retrieve --> Knowledge Base

## Encoding LLM - The Big Idea Behind RAG

- Encoding / Embedding LLM turns questions into vectors (numbers that carries meaning)
- We store all the knowledge in the database and their vectors in the Datastore
- Vector Datastore refers to a Datastore that contains Vectors of each piece of data

### Flow With Encoding

Chat -- Question --> Code -- Prompt --> LLM
Chat <-- Answer -- Code <-- Response -- LLM
Code -- Vectorize --> Encoding LLM
Code -- Retrieve --> Vector Datastore

## Notes

- The Encoding LLM has nothing to do with the LLM (itself) on the right side of the diagram. (auto regressive LLM)
- It is there to help turn the question into a vector.
- The LLM on the right takes information in the natural language (not vector) and
