Ophelia: Week 5, Day 2 - LangChain, Encoders & Vector Stores

## LangChain

LangChain is an open source

- Open source framework launched in October 2022
- Provides a common framework for interfacing with many LLMs
- LangChain v1 released October 2025 with significant changes

### Pros & Cons

- Simplifies the creation of applications using LLMs (e.g. AI Assistants, RAG, Summarization) - fast time to market
- Significant adoption in enterprise
- As APIs for LLMs have matured, converged and simplified, the need for a unifying framework like LangChain has decreased - particularly with OpenAI endpoints.
- LangChain is a more heavyweight abstraction layer than LiteLLM and others, and some of its code can be "legacy"

## Text Splitters

- Text splitters is a part of LangChain responsible for dividing documents into chunks

## Encoder / Embedding Models

- The Encoder Model turns text into a vector Embedding - This is then stored in a vector Database like Chroma.

### Examples

- Word2Vec (2013) - Google
- BERT (2018) - Google
- OpenAI - text embedding-3 small, text embedding-3 large
- Google Gemini-embedding-001
- Hugging Face Sentence Transformers all-MiniLM-L6-v2

## Using LangChain to Load Knowledge Base

- Read in the documents in all folders
- Divide into chunks
- Vectorize and store

Keep in mind: the Encoder turns the text into a vector, The vector store is a Database that does quick lookup

## Popular Encoders

- OpenAI text embedding
- Gemini embedding
- Hugging Face all-MiniLM-L6-v2

## Popular Vectorstores

- Open source: Chroma, Qdrant, FAISS (in memory)
- Paid & scalable: Pinecone, Weaviate
- Mainstream Databases (Postgres, Mongo, Elastic ...)

- The choice of Vector Database is largely unrelated to the vector calculation itself but is a cost / performance tradeoff.

## Steps

- Part A: Divide the document into Chunks
- Part B: Encode the chunks into vectors and put in Chroma
- Part C: Visualize the vectors.
