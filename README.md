# REALTIME-RAG-PIPELINE---MongoDB & Pinecone





Gemma 2 LLM: Takes retrieved docs + user query and generates a final answer

✅MongoDB: Stores raw documents/data.

✅MongoDB Stream Listener: Watches for changes in the database.

✅Pinecone: Stores vector embeddings and handles semantic search

✅All-MiniLM-L6-v2 for lightweight, fast embedding generation

✅Retriever: Finds top-k relevant documents from Pinecone.

✅Groq’s Gemma-2 9B:  LLM Takes retrieved docs + user query and generates a final answer

📦 The system auto-embeds documents on insert via a MongoDB change stream listener, upserts them to Pinecone, and retrieves relevant context on query to generate answers via Groq — all inside Google Colab notebooks.

🧪 Tech Stack:

MongoDB (Change Streams + Metadata)

Pinecone (Vector DB)

Hugging Face Sentence Transformers (all-MiniLM-L6-v2)

Groq API (Gemma-2 9B)

Google Colab + Python

📝 Architecture:

![Editor _ Mermaid Chart-2025-04-06-073618](https://github.com/user-attachments/assets/675220a2-26e6-4be9-9673-e934b0c4d8a5)



