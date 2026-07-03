# Stripe Support AI Assistant

An AI-powered customer support assistant built with **FastAPI**, **ChromaDB**, **Retrieval-Augmented Generation (RAG)**, and **Groq's Llama-3.3-70B-Versatile**.

The application indexes Stripe documentation, retrieves the most relevant document chunks using semantic search, and generates responses grounded strictly in the indexed knowledge base.

---

## Features

- Retrieval-Augmented Generation (RAG)
- Semantic document search with ChromaDB
- Fast inference using Groq API
- Multi-turn conversation support
- Clean Stripe-inspired web interface
- Source-aware document retrieval
- Easy indexing of new documentation

---

## Tech Stack

- Python
- FastAPI
- ChromaDB
- LangChain Text Splitters
- Groq API
- Llama-3.3-70B-Versatile
- HTML / CSS / JavaScript

---

## Project Structure

```
stripe-support-rag/
│
├── app.py
├── llm.py
├── rag.py
├── vectorstore.py
├── requirements.txt
├── README.md
├── logo.png
│
└── data/
    ├── account.txt
    ├── payments.txt
    └── refunds.txt
```

---

## Installation

Clone the repository

```bash
git clone https://github.com/yourusername/stripe-support-rag.git
cd stripe-support-rag
```

Install dependencies

```bash
pip install -r requirements.txt
```

Create an environment variable for your Groq API key.

**Windows**

```powershell
set GROQ_API_KEY=your_api_key
```

**Linux / macOS**

```bash
export GROQ_API_KEY=your_api_key
```

---

## Running the Project

### Step 1 — Build the Vector Database

Index the documentation files located in the `data/` directory.

```bash
python vectorstore.py
```

This creates the ChromaDB vector database used by the application.

### Step 2 — Start the Application

```bash
python app.py
```

Then open

```
http://127.0.0.1:8000
```

---

## How It Works

1. Documentation files are loaded from the `data/` directory.
2. Documents are split into semantic chunks.
3. Chunks are embedded and stored in ChromaDB.
4. User questions are converted into embeddings.
5. The most relevant chunks are retrieved.
6. Retrieved context is sent to Groq's Llama-3.3-70B-Versatile.
7. The model generates a context-grounded response.

---

## Example Questions

- How long do refunds take?
- How can I verify my Stripe account?
- What payment methods are supported?
- How do I update my account information?

---

## License

MIT License
