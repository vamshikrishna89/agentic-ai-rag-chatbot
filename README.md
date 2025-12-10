Note: GitHub’s web viewer sometimes shows “Invalid notebook” for Colab notebooks due to extra widget metadata, but the notebook runs fine when downloaded and opened in Colab.
# Agentic AI RAG Chatbot (PDF → Embeddings → Vector Search → Answers)

This project is a **Retrieval-Augmented Generation (RAG)** chatbot built on top of the ebook:

> **Agentic AI – An Executive's Guide**  
> PDF: https://konverge.ai/pdf/Ebook-Agentic-AI.pdf

The chatbot answers questions **strictly based on this PDF** by:
1. Ingesting and chunking the document
2. Creating vector embeddings
3. Storing them in a vector database (FAISS)
4. Retrieving relevant chunks
5. Generating an answer grounded only in the retrieved context
6. Returning:
   - Final answer  
   - Retrieved context chunks  
   - Confidence score (based on similarity)

---

## 🧰 Tech Stack

- **Language:** Python
- **Notebook:** Google Colab / Jupyter
- **Embeddings:** `sentence-transformers/all-MiniLM-L6-v2`
- **Vector DB:** FAISS (in-memory)
- **LLM (demo):** Local seq2seq model (e.g. FLAN-T5)
- **PDF parsing:** `pypdf`
- **Orchestration:** Custom RAG pipeline (LangGraph-style flow)

> Note: The same architecture can be easily migrated to **OpenAI Embeddings + Pinecone + LangGraph** if desired.

---

## ⚙️ Setup Instructions (How to Run)

### 1. Clone the repo

```bash
git clone https://github.com/<your-username>/agentic-ai-rag-chatbot.git
cd agentic-ai-rag-chatbot
