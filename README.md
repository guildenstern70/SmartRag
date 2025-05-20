# SmartRAG


## Retrieval Augmented Generation
This is a Python Notebook powered by OpenAI and LangChain to implement a small RAG system.

LangChain: https://python.langchain.com/
OpenAI: https://platform.openai.com/docs/overview

This application works in five steps:

1. Load: First, we need to load our data. This is done with Document Loaders.
2. Split: Text splitters break large Documents into smaller chunks. This is useful both for indexing data and passing it into a model, as large chunks are harder to search over and won't fit in a model's finite context window.
3. Store: We need somewhere to store and index our splits, so that they can be searched over later. This is often done using a VectorStore and Embeddings model.
4. Retrieve: Given a user input, relevant splits are retrieved from storage using a Retriever.
5. Generate: A ChatModel / LLM produces an answer using a prompt that includes both the question with the retrieved data.

## Setup

This notebook runs in a Python environment.
To set up a Python environment, see:
https://docs.python.org/3/library/venv.html

### LangSmith Dependencies

With Python up and running, execute

    pip install langchain-text-splitters langchain-community langgraph

You also need to have a LangSmith account and get your LangSmith API key.
We store our data into an in memory vector database, so add it with:

    pip install langchain-core

### OpenAI Dependencies

Then, you must setup OpenAI. Again, register with OpenAI Platform and get an OpenAI API key. 
Install OpenAI AI:

    pip install -U langchain-openai

### Secrets

We need to store API Keys as environment variables, so you need to manually add to
this project a file called .env with the following entries:

LANGSMITH_TRACING=true
LANGSMITH_API_KEY=[Your LangSmith API Key]
OPENAI_API_KEY=[Your OpenAI API Key]


