# Research Paper Question Answering System (RAG)

A Retrieval-Augmented Generation (RAG) application that lets users upload research papers (PDF) and ask natural-language questions about their contents. The system retrieves the most relevant sections of the paper and generates answers grounded strictly in that content, along with source page citations.

## Problem Statement

Build a RAG application that allows users to upload research papers and ask questions about their contents. The system answers questions such as:

- What is the objective of the paper?
- What methodology was used?
- What datasets were used?
- What are the major findings?
- What are the limitations?

## Features

- **PDF Ingestion** — Upload and load any research paper PDF
- **Text Extraction** — Extracts raw text page-by-page
- **Chunking** — Splits text into overlapping chunks for better semantic search
- **Semantic Retrieval** — Finds the most relevant chunks using vector similarity (FAISS)
- **Context-Grounded Generation** — LLM answers only from retrieved context (no hallucination)
- **Source Citation** — Every answer cites the exact page(s) it came from
- **Auto Q&A** — Automatically answers 5 standard research questions on load
- **Interactive Mode** — Ask free-form follow-up questions in a loop

## Tech Stack

| Component | Tool |
|---|---|
| Orchestration | LangChain |
| PDF Loading | PyPDFLoader |
| Chunking | RecursiveCharacterTextSplitter |
| Embeddings | HuggingFace `sentence-transformers/all-MiniLM-L6-v2` |
| Vector Store | FAISS |
| LLM | `Qwen/Qwen2.5-0.5B-Instruct` (local, free, no API key) |

## Architecture
