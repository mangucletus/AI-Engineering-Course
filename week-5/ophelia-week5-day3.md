Ophelia: Week 5, Day 3 - Key Abstractions from LangChain

## Key Abstractions from LangChain

1. LLM
2. Retriever

## Retriever

- A Retriever is an abstraction around Chroma, Datastore + embedded model. Used in retrieving documents closer / similar to another document.

- Many common abstractions like the above can be called with invoke()

  e.g. LLM.invoke()
  e.g. Retriever.invoke()

- ChatOpenAI is one of the LLMs which response to Invoke()

## Retriever Object

```python
retriever = vectorstore.as_retriever()
llm = ChatOpenAI(temperature = 0, model_name = MODEL)

retriever.invoke()
