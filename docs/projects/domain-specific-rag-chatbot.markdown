---
layout: page
title: Domain-Specific RAG Chatbot
permalink: /projects/domain-specific-rag-chatbot/
hide_in_nav: true
---

## Domain-Specific RAG Chatbot

[View on GitHub](https://github.com/batu2244/domain-specific-RAG-chatbot)

A retrieval-augmented generation (RAG) system built to answer questions grounded in a specific document corpus - in this case, Applied Data Science textbook PDFs. Unlike general-purpose chatbots, the system only answers from the provided documents, keeping responses accurate and traceable to source material.

**How It Works**

Documents are loaded and split into overlapping chunks (500 tokens with an 80-token overlap) using a character-based text splitter. Each chunk is embedded and stored in a FAISS vector index. At query time, the user's question is embedded and used to retrieve the most semantically relevant chunks, which are then passed as context to a language model that generates a grounded answer.

**Backend Flexibility**

The system is designed to be backend-agnostic. By default it uses OpenAI's GPT models and OpenAI embeddings, but it can run fully locally by dropping GGUF or `.bin` model files into the `models/` folder - the system auto-discovers them and switches to LlamaCpp with MiniLM embeddings. This makes it usable without an API key or internet connection.

**Interface**

The primary interface is a CLI, with an optional web frontend built in HTML, CSS, and JavaScript. After the first run, the FAISS index is saved to disk so subsequent queries skip the indexing step and load instantly.
