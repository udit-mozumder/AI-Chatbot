# 🤖 AI Agent with RAG + Memory

An intelligent AI assistant that combines **RAG (Retrieval-Augmented Generation)**, **multi-agent reasoning**, and **memory (short-term + long-term)** to deliver context-aware and personalized responses.

---

## 🚀 Overview

This project is a production-style AI system that:

- Answers questions using a **knowledge base (RAG)**
- Uses **LLM for general queries**
- Maintains **conversation memory**
- Stores **long-term memory in Pinecone**
- Dynamically switches between:
  - Structured JSON (for technical queries)
  - Natural language (for normal conversation)

---

## 🧠 Key Features

### 🔹 RAG (Knowledge Base)
- Uses documents from `/data`
- Retrieves context using embeddings
- Powered by Pinecone vector DB

---

### 🔹 Multi-Agent System (CrewAI)
- Intelligent agent decides:
  - Use RAG (document-based)
  - Use LLM (general knowledge)

---

### 🔹 Memory System

#### 🟢 Short-Term Memory
- Stored in session (chat history)
- Maintains conversation context

#### 🔵 Long-Term Memory
- Stored in Pinecone
- Remembers user details across sessions
- Uses **10-minute TTL filtering**

---

### 🔹 Smart Output Handling

**Technical Queries → JSON Output**
```json
{
  "root_cause": "...",
  "explanation": "...",
  "fix": "...",
  "confidence": "high"
}


  General Queries → Natural Response

🔹 Guardrails
Blocks unsafe inputs (e.g. hacking)
Ensures structured responses for technical use
🏗️ Architecture

User Input
↓
Short-Term Memory (Session)
↓
Long-Term Memory (Pinecone)
↓
RAG (Knowledge Base)
↓
Agent Decision (CrewAI)
↓
Final Response

🛠️ Tech Stack
OpenAI (LLM + Embeddings)
LlamaIndex (RAG pipeline)
Pinecone (Vector Database)
CrewAI (Agent orchestration)
Streamlit (UI)
