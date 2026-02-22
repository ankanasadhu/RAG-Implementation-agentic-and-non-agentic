## RAG Implementation: Agentic and Non-Agentic

This repository demonstrates a Proof of Concept (POC) for implementing both non-agentic (deterministic) RAG pipelines and agentic RAG systems using LangChain and LLMs.

The project highlights the architectural and functional differences between traditional Retrieval-Augmented Generation (RAG) workflows and agent-based RAG systems.

* # Overview

This notebook walks through:

Document loading and preprocessing

Text chunking using RecursiveCharacterTextSplitter

Embedding generation

Vector store creation (FAISS)

Building a non-agentic RAG chain

Building an agentic RAG system using LangChain agents

Streaming responses for interactive querying

 * # Architecture
   
 Non-Agentic RAG (Deterministic Chain)

```mermaid
    User_Query[User Query] --> Retriever[Retriever (Vector Store Search)]
    Retriever --> Context[Context Injection into Prompt]
    Context --> LLM[LLM]
    LLM --> Final[Final Answer]
```

Retrieval always happens and it is fixed execution pipeline. It is deterministic and efficient.

 Agentic RAG (Tool-Using Agent)

```mermaid

    User_Query[User Query] --> Agent_Reasoning[Agent Reasoning]
    Agent_Reasoning --> Decision{Call retrieval tool?}
    Decision -->|Yes| Retrieve_Context[Retrieve Context]
    Decision -->|No| Skip[Proceed without retrieval]
    Retrieve_Context --> Final[LLM Generates Final Answer]
    Skip --> Final
 ```

Model dynamically decides when to retrieve supports reasoning + tool usage more flexible for complex queries.


 Tech Stack

Python

LangChain

OpenAI-compatible LLMs

FAISS (vector store)

Jupyter Notebook

* Setup & Installation

Clone the repository:

git clone https://github.com/ankanasadhu/RAG-Implementation-agentic-and-non-agentic.git
cd RAG-Implementation-agentic-and-non-agentic

Install dependencies:

pip install -U langchain langchain-community langchain-openai faiss-cpu

Set your API key:

export OPENAI_API_KEY="your_api_key_here"

Open the notebook:

jupyter notebook

Run all cells sequentially.
