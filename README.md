* RAG Implementation: Agentic and Non-Agentic

This repository demonstrates a Proof of Concept (POC) for implementing both non-agentic (deterministic) RAG pipelines and agentic RAG systems using LangChain and LLMs.

The project highlights the architectural and functional differences between traditional Retrieval-Augmented Generation (RAG) workflows and agent-based RAG systems.

* Overview

This notebook walks through:

Document loading and preprocessing

Text chunking using RecursiveCharacterTextSplitter

Embedding generation

Vector store creation (FAISS)

Building a non-agentic RAG chain

Building an agentic RAG system using LangChain agents

Streaming responses for interactive querying

 * Architecture
 Non-Agentic RAG (Deterministic Chain)
User Query 
    ↓
Retriever (Vector Store Search)
    ↓
Context Injection into Prompt
    ↓
LLM
    ↓
Final Answer

Retrieval always happens

Fixed execution pipeline

Deterministic and efficient

 Agentic RAG (Tool-Using Agent)
User Query
    ↓
Agent Reasoning
    ↓
Decides whether to call retrieval tool
    ↓
Retrieves context (if needed)
    ↓
LLM generates final answer

Model dynamically decides when to retrieve

Supports reasoning + tool usage

More flexible for complex queries

🛠️ Tech Stack

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
