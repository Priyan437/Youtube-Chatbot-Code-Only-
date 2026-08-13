# 🎥 YouTube Video Chatbot

An AI-powered **YouTube Video Chatbot** that allows users to ask questions about a YouTube video's content.

The project uses the video's transcript as the knowledge source and applies a **Retrieval-Augmented Generation (RAG)** pipeline to retrieve relevant portions of the transcript before generating an answer with an LLM.

---

## 🚀 Features

- 🎥 Extracts transcripts from YouTube videos
- ✂️ Splits long transcripts into smaller chunks
- 🧠 Converts transcript chunks into vector embeddings
- 🔎 Performs semantic similarity search using FAISS
- 🤖 Uses an LLM through OpenRouter to generate answers
- 💬 Allows users to ask questions based specifically on the video content
- 📚 Uses Retrieval-Augmented Generation (RAG) to reduce irrelevant responses

---

## 🧠 How It Works

The chatbot follows a Retrieval-Augmented Generation pipeline:

```text
                YouTube Video
                     │
                     ▼
            YouTube Transcript
                     │
                     ▼
          Text Chunking
      RecursiveCharacterTextSplitter
                     │
                     ▼
             Text Chunks
                     │
                     ▼
          Embedding Model
         OpenRouter Embeddings
                     │
                     ▼
             Vector Embeddings
                     │
                     ▼
                  FAISS
            Vector Database
                     │
                     │
User Question ───────┘
       │
       ▼
 Query Embedding
       │
       ▼
 Similarity Search
       │
       ▼
Relevant Transcript Chunks
       │
       ▼
     Prompt
       │
       ▼
    OpenRouter LLM
       │
       ▼
 Generated Answer
