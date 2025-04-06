# REALTIME-RAG-PIPELINE---MongoDB & Pinecone

A modular, real-time RAG system that connects:

✅ MongoDB (as a metadata store) to store and track documents
✅ Pinecone (as a vector store) to handle semantic retrieval
✅ All-MiniLM-L6-v2 for lightweight, fast embedding generation
✅ Groq’s Gemma-2 9B LLM for fast and accurate responses

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

