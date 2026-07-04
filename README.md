# 📚 RAG Research Agent

<p align="center">
  <strong>An intelligent Retrieval-Augmented Generation (RAG) Research Agent built with LangChain, Google Gemini, ChromaDB, Hugging Face Embeddings, and Tavily Search.</strong>
</p>

<p align="center">

<img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white">

<img src="https://img.shields.io/badge/LangChain-Agent-1C3C3C?style=for-the-badge">

<img src="https://img.shields.io/badge/Google-Gemini-4285F4?style=for-the-badge&logo=google">

<img src="https://img.shields.io/badge/ChromaDB-Vector%20Store-7E57C2?style=for-the-badge">

<img src="https://img.shields.io/badge/HuggingFace-Embeddings-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black">

<img src="https://img.shields.io/badge/Tavily-Web%20Search-0A84FF?style=for-the-badge">

<img src="https://img.shields.io/badge/Google-Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white">

</p>

<p align="center">
<img src="assets/project-overview.png" width="100%" alt="Project Overview">
</p>

---

## 📖 Overview

This project demonstrates how to build an intelligent **Retrieval-Augmented Generation (RAG) Research Agent** capable of answering questions from research papers while retrieving up-to-date information from the web whenever necessary.

Unlike a traditional chatbot that relies only on an LLM, this agent dynamically decides whether to retrieve information from a research paper or search the web, and then combines the retrieved context with **Google Gemini** to generate accurate, context-aware responses.

---

## ✨ Features

- 📄 Load research papers from PDF
- ✂️ Split documents into semantic chunks
- 🧠 Generate embeddings using Hugging Face Sentence Transformers
- 🗄️ Store embeddings in ChromaDB
- 🔍 Semantic search over research papers
- 🌐 Real-time web search using Tavily
- 🤖 Google Gemini powered response generation
- 🧩 LangChain Agent with dynamic tool selection
- 💬 Research question answering with document + web knowledge

---

## 🏗️ Architecture

```
                    User Question
                          │
                          ▼
               LangChain Research Agent
                          │
        ┌─────────────────┴─────────────────┐
        │                                   │
        ▼                                   ▼
 PDF Retrieval Tool               Tavily Search Tool
        │                                   │
        ▼                                   ▼
 Chroma Vector DB                 Web Search Results
        │                                   │
        └─────────────────┬─────────────────┘
                          ▼
                 Google Gemini 2.5 Flash
                          │
                          ▼
                   Final Response
```

---

## ⚙️ Workflow

1. Load the research paper using **PyPDFLoader**
2. Split the document using **RecursiveCharacterTextSplitter**
3. Generate embeddings using **all-mpnet-base-v2**
4. Store embeddings in **ChromaDB**
5. Create a semantic retrieval tool
6. Create a Tavily Search tool
7. Build a LangChain Agent with both tools
8. Agent decides whether to search the PDF or the web
9. Google Gemini generates the final answer

---

## 🛠️ Tech Stack

| Category | Technology |
|-----------|------------|
| Language | Python |
| Development | Google Colab |
| Framework | LangChain |
| LLM | Google Gemini 2.5 Flash |
| Embeddings | Hugging Face (`all-mpnet-base-v2`) |
| Vector Database | ChromaDB |
| Web Search | Tavily Search |
| PDF Loader | PyPDF |

---

## 📂 Project Structure

```
RAG-Research-Agent/
│
├── assets/
│   └── project-overview.png
│
├── RAG_Research_Agent.ipynb
├── README.md
├── requirements.txt
├── LICENSE
└── .gitignore
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Google Colab
- Google Gemini API Key
- Tavily API Key

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Configure API Keys

Store the following keys using **Google Colab Secrets**.

```
gemini_api_key
tavily_apikey
```

### Run

1. Open **RAG_Research_Agent.ipynb**
2. Upload a research paper
3. Add API keys in Colab Secrets
4. Run all notebook cells
5. Ask research-related questions

---

## 💬 Example Query

> Compare the attention mechanism from the paper with recent improvements like Flash Attention and explain which approach would be more suitable for my college project.

The agent will:

- Retrieve relevant sections from the research paper
- Search the web for newer developments (if required)
- Combine both sources
- Generate a comprehensive response using Google Gemini

---

## 🔮 Future Improvements

- Multi-document support
- Chat history & memory
- Streamlit web interface
- Hybrid Retrieval (BM25 + Vector Search)
- Source citations
- Multiple LLM support

---

## 📄 License

This project is licensed under the **MIT License**.

---

## 👨‍💻 Author

**Prahla**

If you found this project useful, consider ⭐ starring the repository.
