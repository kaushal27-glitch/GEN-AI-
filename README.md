GEN AI
RAG-Powered Research Document Analyzer

A production-ready Retrieval-Augmented Generation (RAG) system for analyzing research documents, powered by FastAPI, LangChain, and vector embeddings. Upload PDFs, ask questions, and get answers with source attribution.

Why This Project? This is a 2024-2025 hiring focus area that demonstrates you can build beyond simple chatbots — you understand production RAG architecture, vector databases, prompt engineering, and LLM orchestration.


🎯 Quick Start (5 minutes)

Prerequisites


Python 3.10+
OpenAI API key (or local Ollama)
~2GB disk space for dependencies


Installation

bash# Clone and setup
git clone https://github.com/your-username/rag-document-analyzer.git
cd rag-document-analyzer

# Create virtual environment
python -m venv venv
source venv/bin/activate  # macOS/Linux
# OR
venv\Scripts\activate  # Windows

# Install dependencies
pip install -r requirements.txt

# Configure environment
cp .env.example .env
# Edit .env and add your OPENAI_API_KEY
nano .env

Run API Server

bash# Start FastAPI server (development)
python src/api/main.py

# Or with uvicorn directly
uvicorn src.api.main:app --reload --host 0.0.0.0 --port 8000

API is live at: http://localhost:8000
Swagger Docs: http://localhost:8000/docs

Test It

bash# Health check
curl http://localhost:8000/health

# Upload a document
curl -X POST http://localhost:8000/upload \
  -F "file=@path/to/research.pdf"

# Query the documents
curl -X POST http://localhost:8000/query \
  -H "Content-Type: application/json" \
  -d '{"question": "What are the main findings?", "use_rag": true}'
