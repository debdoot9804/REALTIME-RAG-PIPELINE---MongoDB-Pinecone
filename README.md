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

📝 Diagram Flow Breakdown

🔁 Ingestion Path


[ MongoDB ] ──► [ MongoDB Change Stream Listener ] ──► [ MiniLM Embeddings ]
        │                                                      │
        ▼                                                      ▼
[ Metadata Store ]                                     [ Pinecone Vector Store ]

----------------------------------------------------------------------------------------------------------------------

🔍 Retrieval + Generation Path

[ User Query ] ──► [ MiniLM (Embedding) ] ──► [ Pinecone Search (Top-k) ] ──►
        ▼
[ Retrieved Context ] ──► [ Groq API (Gemma-2 9B) ] ──► [ Final Response ]

----------------------------------------------------------------------------------------------------------------------

