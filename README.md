````markdown
# 📚 RAG Research Agent

> An intelligent **Retrieval-Augmented Generation (RAG) Research Agent** built with **LangChain**, **Google Gemini**, **ChromaDB**, **Hugging Face Embeddings**, and **Tavily Search**.

<p align="center">

<img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white"/>

<img src="https://img.shields.io/badge/LangChain-Agent-1C3C3C?style=for-the-badge"/>

<img src="https://img.shields.io/badge/Google-Gemini-4285F4?style=for-the-badge&logo=google"/>

<img src="https://img.shields.io/badge/ChromaDB-Vector%20Store-7E57C2?style=for-the-badge"/>

<img src="https://img.shields.io/badge/HuggingFace-Embeddings-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black"/>

<img src="https://img.shields.io/badge/Tavily-Web%20Search-0A84FF?style=for-the-badge"/>

<img src="https://img.shields.io/badge/Google-Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white"/>

</p>

<p align="center">
<img src="assets/project-overview.png" alt="RAG Research Agent Overview" width="100%">
</p>

---

## 📖 Overview

This project demonstrates how to build an intelligent **Retrieval-Augmented Generation (RAG) Research Agent** capable of answering questions from a research paper while retrieving up-to-date information from the web whenever required.

Instead of relying solely on a language model, the agent intelligently chooses between two information sources:

- 📄 **Semantic Search** over a research paper stored in **ChromaDB**
- 🌐 **Real-time Web Search** using **Tavily Search**

The retrieved context is then combined with **Google Gemini** to generate accurate, context-aware responses.

---

## ✨ Features

- 📄 Load research papers from PDF
- ✂️ Split documents into semantic chunks
- 🧠 Generate vector embeddings using Hugging Face
- 🗄️ Store embeddings in ChromaDB
- 🔍 Retrieve relevant document context using semantic search
- 🌐 Search the web using Tavily when required
- 🤖 Generate responses with Google Gemini
- 🧩 LangChain Agent that dynamically chooses the appropriate tool
- 💬 Answer research questions using both document knowledge and live web information

---

## 🏗️ Architecture

```text
                           User Question
                                 │
                                 ▼
                     LangChain Research Agent
                                 │
             ┌───────────────────┴───────────────────┐
             │                                       │
             ▼                                       ▼
      PDF Retrieval Tool                     Tavily Search Tool
      (Semantic Search)                      (Web Search)
             │                                       │
             ▼                                       ▼
      Chroma Vector Database                Latest Web Results
             │                                       │
             └───────────────────┬───────────────────┘
                                 ▼
                     Google Gemini 2.5 Flash
                                 │
                                 ▼
                          Final Response
```

---

## ⚙️ Workflow

1. Load a research paper using **PyPDFLoader**.
2. Split the document into semantic chunks using **RecursiveCharacterTextSplitter**.
3. Generate embeddings using the **all-mpnet-base-v2** sentence transformer.
4. Store the embeddings in **ChromaDB**.
5. Create a PDF retrieval tool for semantic search.
6. Create a Tavily Search tool for retrieving current information.
7. Build a LangChain Agent with both tools.
8. The agent determines whether to retrieve from the document or search the web.
9. Google Gemini generates the final response.

---

## 🛠️ Tech Stack

| Category | Technology |
|----------|------------|
| Language | Python |
| Development Environment | Google Colab |
| Framework | LangChain |
| LLM | Google Gemini 2.5 Flash |
| Embeddings | Hugging Face Sentence Transformers (`all-mpnet-base-v2`) |
| Vector Database | ChromaDB |
| Web Search | Tavily Search |
| PDF Loader | PyPDF |

---

## 📁 Project Structure

```text
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
- Google Colab (Recommended)
- Google Gemini API Key
- Tavily API Key

---

### Installation

```bash
pip install -r requirements.txt
```

---

### Configure API Keys

Store the following keys using **Google Colab Secrets**:

```text
gemini_api_key
tavily_apikey
```

No API keys are hardcoded inside the notebook.

---

### Run the Project

1. Open **RAG_Research_Agent.ipynb** in Google Colab.
2. Upload the research paper you want to analyze.
3. Add your API keys using Colab Secrets.
4. Run all notebook cells from top to bottom.
5. Ask research-related questions.

---

## 💬 Example Query

> Compare the attention mechanism from the paper with recent improvements like Flash Attention, and tell me which approach would be better for my college project.

The agent will:

- Retrieve relevant information from the research paper.
- Search the web for newer information if necessary.
- Combine both sources to generate a comprehensive answer using Google Gemini.

---

## 🚀 Future Improvements

- Multi-document support
- Conversation memory
- Streamlit web application
- Hybrid Retrieval (BM25 + Vector Search)
- Source citations
- Support for additional LLM providers

---

## 👨‍💻 Author

**Prahla**

---

⭐ If you found this project helpful or interesting, consider giving the repository a star!
````
