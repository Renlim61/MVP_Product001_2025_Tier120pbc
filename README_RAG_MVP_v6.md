# Phase 1 – GenAI RAG MVP (Google Colab)

This repository contains a **working MVP of a Retrieval-Augmented Generation (RAG) assistant** designed to run in [Google Colab](https://colab.research.google.com/) with zero infrastructure cost.  
It enables **single-tenant** operation using a **Bring Your Own OpenAI Key** approach.

---

## ✨ Features

- 📄 **Multi-file ingestion** — PDF, DOCX, and TXT support
- 🧠 **Text chunking** with configurable size and overlap
- 🔍 **FAISS in-memory vector search** with cosine similarity
- 🤖 **OpenAI embeddings** (`text-embedding-3-small` with automatic fallback to `text-embedding-3-large`)
- 💬 Interactive **Gradio UI** with:
  - File upload and ingestion tab
  - Document selection per query
  - Natural language Q&A with **citations**
- 🪣 **Optional save/load** of ingested state to Google Drive
- 🔐 **No server** required — runs entirely in Colab

---

## 🚀 Quick Start

### 1. Open in Google Colab
Upload the `Phase1_RAG_MVP_clean_v6.ipynb` notebook to your Google Drive or directly open it in [Colab](https://colab.research.google.com/).

### 2. Run the Notebook
Execute all cells. The notebook installs dependencies, initializes FAISS and Gradio, and launches the app automatically.

### 3. Add Your OpenAI API Key
Paste your OpenAI key in the UI textbox.  
This key is only stored in the current Colab runtime.

### 4. Ingest Files
- Supported types: `.pdf`, `.docx`, `.txt`
- Ingest multiple files at once
- Successfully ingested files appear in the shared document selector

### 5. Ask Questions
- Select one or more ingested documents
- Type your question and click **Ask**
- The system retrieves top-K relevant chunks and generates an answer with citations

### 6. (Optional) Save / Load State
- Mount Google Drive
- Save your current FAISS index and chunks
- Load saved state in future sessions

---

## 🧪 Example Use

1. Upload a `sample.txt` file with:  
   ```
   The capital of France is Paris.
   ```
2. Ingest the file.
3. Ask: `What is the capital of France?`
4. Response:  
   ```
   The capital of France is Paris. [1]

   Sources:
   [1] sample.txt (chunk 0)
   ```

---

## 🧰 Tech Stack

- [Gradio](https://www.gradio.app/) — lightweight UI
- [FAISS](https://faiss.ai/) — in-memory vector search
- [OpenAI API](https://platform.openai.com/) — embeddings and chat completions
- [pypdf](https://pypi.org/project/pypdf/) — PDF text extraction
- [python-docx](https://pypi.org/project/python-docx/) — DOCX text extraction

---

## 🛠️ Local Development Notes

- Designed for use in Google Colab (no server required).
- Can be adapted to run locally in Jupyter Notebook.
- Uses in-memory FAISS index — re-ingest required after runtime reset unless saved to Drive.

---

## 🧭 Next Steps (Phase 2 Ideas)

- Persistent vector store (e.g., Chroma, Weaviate)
- Multi-tenant support (user isolation)
- Metadata filters
- OCR support for scanned PDFs
- Query analytics and usage tracking
- Lightweight authentication

---

## 📝 License

This project is released under the MIT License.  
Feel free to fork, modify, and extend it.

---

## 🙌 Acknowledgments

- [OpenAI](https://openai.com)
- [Gradio](https://www.gradio.app/)
- [FAISS](https://faiss.ai/)
- [Google Colab](https://colab.research.google.com/)
