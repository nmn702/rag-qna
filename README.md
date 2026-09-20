# PDF RAG Question Answering

A simple **Retrieval-Augmented Generation (RAG)** application that allows users to ask questions about multiple research papers and generate answers using retrieved document context.

## Overview

The application:

* Loads multiple PDF research papers.
* Splits documents into smaller chunks.
* Generates embeddings using **HuggingFace Sentence Transformers**.
* Stores embeddings in a local **ChromaDB** vector store.
* Retrieves the most relevant document chunks for a question.
* Uses **Google Gemini 2.0 Flash** to generate the answer.
* Provides an interactive **Streamlit** interface.

## Architecture

```text
PDF Documents
     ↓
PyPDFLoader
     ↓
Text Chunking
     ↓
HuggingFace Embeddings
     ↓
Chroma Vector Store
     ↓
Similarity Search
     ↓
Relevant Context
     ↓
Gemini 2.0 Flash
     ↓
Generated Answer
```

## Tech Stack

* **Python**
* **LangChain**
* **LangGraph**
* **ChromaDB**
* **HuggingFace Sentence Transformers**
* **Google Gemini**
* **PyPDF**
* **Streamlit**

### Embedding Model

```text
sentence-transformers/all-mpnet-base-v2
```

### LLM

```text
gemini-2.0-flash
```

## Documents

The application currently loads:

```text
bert.pdf
graphs.pdf
attention.pdf
gpt3.pdf
llama.pdf
```

## RAG Configuration

```python
chunk_size = 2000
chunk_overlap = 200
top_k = 5
```

The application retrieves the **5 most relevant chunks** for each question before generating the answer.

## Running the Application

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Run Streamlit:

```bash
streamlit run app.py
```

Enter your **Google Gemini API key** and ask questions about the loaded PDFs.

## Concepts Used

* Retrieval-Augmented Generation (RAG)
* Vector Embeddings
* Semantic Search
* Vector Databases
* Document Chunking
* LLM-based Question Answering
* LangGraph Workflows
* Streamlit

> **Note:** This project is intended for learning and demonstrates a basic RAG pipeline for querying multiple PDF documents.
