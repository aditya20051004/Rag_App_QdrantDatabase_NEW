🚀 RAG App (Retrieval-Augmented Generation)

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Streamlit](https://img.shields.io/badge/Frontend-Streamlit-red)
![Qdrant](https://img.shields.io/badge/VectorDB-Qdrant-green)
![LLM](https://img.shields.io/badge/LLM-OpenAI%2FGroq-purple)

---

🧠 Overview

This project implements a Retrieval-Augmented Generation (RAG) pipeline that allows users to:

- Upload PDF documents 📄
- Convert them into embeddings 🔢
- Store them in a vector database (Qdrant) 🗄️
- Perform semantic search 🔍
- Generate context-aware responses using LLM 🤖

---

⚙️ Tech Stack

- Frontend: Streamlit
- Backend: FastAPI + Inngest
- Vector DB: Qdrant
- LLM: OpenAI / Groq
- Orchestration: uv

---

🏗️ Architecture

User → Streamlit UI
     → FastAPI Backend
     → Embeddings
     → Qdrant (Vector DB)
     → LLM (OpenAI/Groq)
     → Response

---

🚀 Run Locally (Step-by-Step)

1️⃣ Clone the repository

git clone <your-repo-url>
cd <repo-name>

---

2️⃣ Install dependencies

uv init
uv add fastapi inngest llama-index-core llama-index-readers-file python-dotenv qdrant-client uvicorn streamlit openai

---

3️⃣ Setup environment variables

Create a ".env" file:

OPENAI_API_KEY=your_api_key_here

👉 Get API key from OpenAI dashboard

---

4️⃣ Start Backend (FastAPI)

uv run uvicorn main:app --reload

---

5️⃣ Start Inngest

npx inngest-cli@latest dev -u http://localhost:8000/api/inngest --no-discovery

---

6️⃣ Run Qdrant (Vector Database using Docker)

Make sure Docker is installed, then:

docker run -d \
  -p 6333:6333 \
  -v "$(pwd)/qdrant_storage:/qdrant/storage" \
  qdrant/qdrant

---

7️⃣ Launch Streamlit UI

uv run streamlit run streamlit_app.py

---

🎯 Usage

1. Open the Streamlit app in browser
2. Upload a PDF document 📄
3. Ask questions related to the document
4. Get context-aware responses 🤖

---

⚠️ Notes

- API keys are not included for security reasons
- Qdrant runs locally via Docker
- Ensure all services are running before using the app

---

💡 Future Improvements

- Deploy on cloud (Streamlit Cloud / Render)
- Replace local Qdrant with cloud instance
- Add authentication
- Improve chunking & retrieval strategies

---

👨‍💻 Author

Aditya Majumder

---

⭐ If you like this project

Give it a star ⭐ on GitHub!
