Ophelia: Week 5, Day 5 - 10 RAG Advanced Techniques

## 10 RAG Advanced Techniques

1. Chunking R&D: experiment with chunking strategy
2. Encoder R&D: select the best Encoder model based on a test set
3. Improve prompts: General Context, the current date, relevant context and history
4. Document pre-processing: use an LLM to make the chunks and/or text for encoding.
5. Query rewriting: use an LLM to convert the user's question to a RAG query.
6. Query expansion: use an LLM to turn the question into multiple RAG queries
7. Re-ranking: use an LLM to sub-select from RAG results.
8. Hierarchical: use an LLM to summarize at multiple levels
9. Graph RAG: retrieve content closely related to similar documents
10. Agentic RAG: use Agents for retrieval, combining with memory and Tools such as SQL

## Steps in doing LLM Semantic Rewriting

1. Fetch documents from the knowledge base, like LangChain
2. Call an LLM to turn documents into chunks
3. Store the chunks in Chroma
