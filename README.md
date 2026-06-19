# 🔍 OPEN-SOURCE FINDING_AI

> **An AI-Powered Job Discovery and Recruitment Platform** with privacy-first local LLMs, intelligent candidate-to-job matching, skill graph mapping, and delta resume storage.

---

## 🌟 Overview

**FINDING_AI** is a state-of-the-art, privacy-centric job discovery and recruitment platform. Traditional recruitment systems rely on simple keyword matching or upload resumes to third-party cloud LLM APIs, exposing sensitive Personal Identifiable Information (PII) and incurring significant operational costs.

FINDING_AI solves this by:
1. Running **local LLMs (via Ollama)** on-premise to parse, extract, and clean resume details securely.
2. Building a **Semantic Skill Graph** using vector embeddings to match profiles to jobs by *intent* and *context*, not just keywords.
3. Implementing a **Resume Archetype & Delta Storage System** to store only the variations between profiles and job classes, minimizing database bloat.
4. Using **Continuous Feedback Loops** that update matching weights in real-time as recruiters review and hire candidates.

---

## 🧱 Project Modules Overview

The platform is designed around 15 core architectural modules:

1. **User Authentication & Profile Management**: Secure registration/login paths for job seekers and employers with role-based access controls.
2. **Resume Upload & Processing**: PDF, DOCX, and TXT upload handlers, raw text extraction, and metadata management.
3. **Local LLM Resume Analysis**: Entity extraction (skills, projects, work experience) using local models via Ollama.
4. **Resume Archetype & Delta Storage**: Storing baseline career archetypes and tracking candidate profiles via optimized delta diffs.
5. **Skill Graph & Semantic Representation**: A semantic skill ontology supporting vector embeddings and temporal skill decay models.
6. **Job Posting Management**: Employer dashboard and job creation wizards.
7. **AI Candidate Matching Engine**: Quantitative matching algorithms that combine skills, experience, and certifications into explainable matching reports.
8. **AI Resume Improvement Assistant**: Proactively suggesting improvements, detecting missing skills, and recommending courses/certifications.
9. **Employer Feedback Learning System**: Feedback interface that updates AI matching weights based on real-time employer reviews.
10. **Search & Recommendation Engine**: Semantic candidate and job searches powered by high-performance vector databases.
11. **Analytics Dashboard**: Custom interactive charts for candidate profiles and employer success rates.
12. **API Development**: A scalable, fully documented (OpenAPI/Swagger) versioned REST API.
13. **Frontend Development**: A responsive, user-friendly React application for employers and candidates.
14. **Database & Infrastructure**: PostgreSQL with `pgvector` indexing and database optimization strategies.
15. **Security & Privacy**: Field-level data encryption (PII protection), secure file storage, and GDPR-ready data portability features.

---

## 🛠️ Technology Stack

* **Frontend**: React (TypeScript), Vite, TailwindCSS (for custom UI), Chart.js / Recharts
* **Backend**: Python (FastAPI), Pydantic, SQLAlchemy
* **Local LLM Orchestration**: Ollama (supported models: `llama3`, `mistral`, `phi3`)
* **Vector Embeddings**: HuggingFace Sentence-Transformers (`all-MiniLM-L6-v2`)
* **Databases**: PostgreSQL (with `pgvector` extension)
* **File Storage**: Local filesystem (development) / S3-compatible storage (production)

---

## 📂 Directory Layout

```text
OPEN-SOURCE_FINDING_AI/
├── .github/                   # CI/CD Workflows, Pull Request and Issue Templates
├── docs/                      # Extensive Guides & Specifications
│   ├── architecture.md        # Mermaid diagrams, Pipeline details, DB schema
│   └── setup.md               # Detailed Local LLM, Backend, and Frontend Setup
├── CONTEXT/                   # Context documentation
├── README.md                  # Project Homepage (This file)
├── CONTRIBUTING.md            # Workflow instructions for human contributors
├── AI_RULES.md                # Strict guidelines for AI Coding Agents
├── ROADMAP.md                 # Project Phase Plan
├── TASKS.md                   # Live features & task registry (assign yourself here!)
└── CODE_OF_CONDUCT.md         # Community standard guidelines
```

---

## 🚀 Quick Start & Documentation

* 📖 **Local Installation & Setup**: Learn how to configure your local database, install dependencies, and run Ollama in [docs/setup.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/docs/setup.md).
* 📐 **System Architecture & Data Pipelines**: Read about our storage models, skill graph, and matching pipelines in [docs/architecture.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/docs/architecture.md).
* 🗺️ **Platform Roadmap**: View our phases of development in [ROADMAP.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/ROADMAP.md).
* 📋 **Current Active Tasks**: Claim a task to build or verify in [TASKS.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/TASKS.md).

---

## 👥 How to Contribute

This project maintains a unique registry-based workflow where contributors assign themselves to tasks in `TASKS.md` as either a **Feature Adder (Role 1)** or a **Bug Fixer / Verifier (Role 2)**. 

Please review:
1. **[CONTRIBUTING.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/CONTRIBUTING.md)** for contributor workflows.
2. **[AI_RULES.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/AI_RULES.md)** if you are using an AI coding assistant.
3. **[CODE_OF_CONDUCT.md](file:///c:/Users/anshul%20prajapati/OneDrive/Desktop/OPEN-SOURCE_FINDING_AI/CODE_OF_CONDUCT.md)** for community standards.

---

## 📄 License

This project is licensed under the Apache License 2.0. See the LICENSE file for details (to be created upon project initiation).
