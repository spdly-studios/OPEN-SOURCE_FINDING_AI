# ⚙️ FINDING_AI Local Setup Guide

This guide walks you through setting up the frontend, backend, database, and local LLM environment for **FINDING_AI**.

---

## 🛠️ Prerequisites

Before you begin, ensure you have the following installed on your machine:
* **Operating System**: Windows 10/11, macOS, or modern Linux (Ubuntu 22.04+)
* **Python**: Version `3.10` or `3.11`
* **Node.js & NPM**: Node `v18` or `v20` (NPM `v9` or `v10`)
* **PostgreSQL**: Version `15` or `16` with **pgvector** installed
* **Ollama**: For running local LLMs

---

## 🧠 1. Local LLM Setup (Ollama)

FINDING_AI uses **Ollama** to run models locally, guaranteeing candidate data privacy.

### Step 1: Install Ollama
* **Windows**: Download and run the installer from the [Ollama Download Page](https://ollama.com/download/windows).
* **macOS / Linux**: Follow the instructions on the Ollama homepage.

### Step 2: Download Models
Open your terminal/command prompt and pull the default model used for resume extraction and advice:
```bash
# Pull the default LLM (Llama3 8B parameter model, ~4.7 GB)
ollama pull llama3

# Pull the default embedding model (for skill mapping)
ollama pull nomic-embed-text
```

### Step 3: Run and Verify Ollama
Ollama runs as a background service by default on Windows/macOS. You can verify it is active by opening `http://localhost:11434/` in your browser, or running:
```bash
curl http://localhost:11434/
# Output should be: "Ollama is running"
```

---

## 🗄️ 2. Database Setup (PostgreSQL + pgvector)

Our semantic search and candidate recommendation systems rely on storing skill and profile vector embeddings.

### Step 1: Install pgvector
* **Windows**: Download the binary installer matching your PostgreSQL version or build from source. For pre-packaged bundles, tools like EnterpriseDB or Docker make it simple.
* **Docker Option (Recommended)**: If you prefer Docker, you can run a pre-compiled postgres-pgvector image:
  ```bash
  docker run --name finding-postgres -e POSTGRES_PASSWORD=mysecretpassword -p 5432:5432 -d pgvector/pgvector:pg16
  ```

### Step 2: Initialize Database and Enable Vector Extension
Connect to your PostgreSQL server using `psql` or an admin GUI (like pgAdmin or DBeaver) and run:
```sql
-- Create the project database
CREATE DATABASE finding_ai_db;

-- Connect to finding_ai_db and enable pgvector
\c finding_ai_db;
CREATE EXTENSION IF NOT EXISTS vector;
```

---

## 🐍 3. Backend Setup (FastAPI)

### Step 1: Clone & Navigate to Backend
Ensure you are in the workspace root directory, then navigate to your backend folder (e.g., `backend/`):
```bash
cd backend
```

### Step 2: Create a Virtual Environment
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows (PowerShell):
.\venv\Scripts\Activate.ps1
# On Windows (CMD):
.\venv\Scripts\activate.bat
# On macOS/Linux:
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install --upgrade pip
pip install -r requirements.txt
```
*(Dependencies include: `fastapi`, `uvicorn`, `sqlalchemy`, `pgvector`, `pydantic`, `pydantic-settings`, `python-jose`, `passlib`, `python-multipart`, `requests`, `sentence-transformers`)*

### Step 4: Configure Environment Variables
Copy the example environment file from the repository root:
```bash
cp ../.env.example .env
```
Open `.env` and fill in your local credentials:
* Set `DATABASE_URL` to `postgresql://<user>:<password>@localhost:5432/finding_ai_db`
* Verify `OLLAMA_API_URL` is set to `http://localhost:11434`

### Step 5: Run Database Migrations
Generate and run migrations to create the database schemas:
```bash
alembic upgrade head
```

### Step 6: Start the Backend Server
```bash
uvicorn main:app --reload --port 8000
```
Verify the backend is active by checking the Swagger UI at `http://localhost:8000/docs`.

---

## 💻 4. Frontend Setup (React + Vite)

### Step 1: Navigate to Frontend
In a new terminal window, navigate to the frontend folder (e.g., `frontend/`):
```bash
cd frontend
```

### Step 2: Install NPM Dependencies
```bash
npm install
```

### Step 3: Configure Frontend Environment
Create a `.env` file in the frontend folder:
```text
VITE_API_URL=http://localhost:8000/api/v1
```

### Step 4: Start the Development Server
```bash
npm run dev
```
Open the URL shown in the terminal (usually `http://localhost:5173`) to view the application interface.

---

## 🛠️ Verification Checklist
After setting up the project:
1. Log in to the Frontend.
2. Register a new user as a Job Seeker.
3. Upload a sample PDF resume.
4. Verify that the file upload succeeds, the backend console displays LLM requests going to Ollama, and your Candidate Profile is successfully populated with extracted skills and experiences.
