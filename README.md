# 🤖 Multilingual RAG-Based IT Support Ticket Resolution System

A Retrieval-Augmented Generation (RAG) system designed for automatic resolution of IT support tickets in multiple languages using historical ticket data, semantic search (ChromaDB), and Google Gemini 2.0 Flash LLM.

---

## 🔍 Overview

This project implements an intelligent, multilingual support assistant that:
- Detects the language of a support query (English, German, French, Spanish)
- Retrieves semantically similar resolved tickets from ChromaDB
- Uses Google Gemini to generate grounded, context-aware responses

---

## ✅ Features

- 🌍 **Multilingual Support**: Handles queries in `en`, `de`, `fr`, and `es`
- 🧠 **Semantic Search**: Retrieves similar tickets using multilingual sentence embeddings
- ⚙️ **RAG Pipeline**:
  - Embeds tickets using `sentence-transformers`
  - Stores and retrieves from **ChromaDB**
- 🤖 **LLM Response Generation**:
  - Integrated with **Google Gemini 2.0 Flash** via LangChain
  - Prompt templates tailored by language and context
- 🎯 **Confidence Score + Reasoning**:
  - Provides confidence level for each generated response
  - Includes explanation of ticket similarity

---

## 🧠 Tech Stack

| Component          | Library / Tool                          |
|--------------------|------------------------------------------|
| Embedding Model    | `sentence-transformers`                  |
| Vector Store       | `ChromaDB`                               |
| Language Detection | `langdetect`                             |
| LLM                | `Google Gemini 2.0 Flash` via LangChain  |
| Backend            | Python (Jupyter Notebook/Colab Ready)    |

---

## 🚀 How It Works

1. **Load Datasets**:
   - Preprocessed support ticket data per language
2. **Build Vector Index**:
   - Embed `rag_content` field and store in ChromaDB
3. **User Query**:
   - Auto-detects language
   - Retrieves top-k similar tickets by cosine similarity
4. **Generate Answer**:
   - LLM prompt created with ticket context
   - Gemini returns a grounded and actionable solution

---

## 📁 Project Structure

├── rag_system.py # Main RAG class (MultilingualRAGSystem)
├── datasets/
│ ├── rag_ready_english_tickets.csv
│ ├── rag_ready_french_tickets.csv
│ ├── rag_ready_combined_tickets.csv
├── notebook_example.ipynb # Jupyter/Colab interactive test notebook
├── README.md # Project description (this file)
├── requirements.txt # All Python dependencies
