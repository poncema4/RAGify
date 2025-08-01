# RAGify

RAGify is a Retrieval Augmented Generation (RAG) chatbot application that allows you to query your own PDF documents using OpenAI's language models. It uses LangChain, ChromaDB, and Gradio to provide a conversational interface that answers questions based solely on the content of your uploaded documents.

---

## Requirements

- Python 3.8+
- OpenAI API key

---

## Features

- **PDF Ingestion:** Automatically loads and splits PDF files from the `data/` directory
- **Embeddings:** Uses OpenAI's `text-embedding-3-large` model to generate vector embeddings for document chunks
- **Vector Store:** Stores and retrieves document embeddings using ChromaDB for fast semantic search
- **Conversational Chatbot:** Gradio-powered chat interface that streams answers based only on your documents
- **Secure:** Keeps sensitive information (API keys, data, embeddings, and environment) out of version control

---

## How It Works

1. **Ingest Documents:**  
   The `ingest_database.py` script loads all PDFs from the `data/` folder, splits them into manageable chunks, generates embeddings, and stores them in a local ChromaDB instance.

2. **Chatbot Interface:**  
   The `chatbot.py` script launches a Gradio web interface. When you ask a question, it retrieves the most relevant document chunks from ChromaDB and uses an OpenAI model to generate an answer based only on those chunks.

---

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/RAGify.git
cd RAGify
```

### 2. Set Up a Virtual Environment

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Add Your OpenAI API Key

Create a `.env` file in the project root:

```
OPENAI_API_KEY="your-openai-api-key"
```

### 5. Add Your PDF Files

Place your PDF files in the `data/` directory.

### 6. Ingest Your Documents

```bash
python ingest_database.py
```

### 7. Launch the Chatbot

```bash
python chatbot.py
```

The Gradio interface will open in your browser

---

## File Structure

```
RAGify/
│
├── .env*              # Your OpenAI API key (not tracked by git)
├── .gitignore         # Ignores .env, .venv, chroma_db
├── data/              # Place your PDF files here
├── chroma_db/         # ChromaDB vector store (auto-generated)
├── .venv/             # Python virtual environment
├── ingest_database.py # Script to ingest and embed documents
├── chatbot.py         # Gradio chatbot interface
├── requirements.txt   # Python dependencies
└── README.md          # Project documentation
```

---

## Security & Privacy

- **Sensitive files** like `.env`, `.venv/`, and `chroma_db/` are excluded from version control via `.gitignore`.
- **Never share your `.env` file or API keys.**

---

## Demo

<img width="1480" height="910" alt="image" src="https://github.com/user-attachments/assets/9c311e70-4ab7-4c13-94dd-5abb694917a1" />

---
