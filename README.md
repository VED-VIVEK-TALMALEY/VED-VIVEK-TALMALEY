# I Build Shipping AI Systems
**Multi-Agent Pipelines · LLM Engineering · Geospatial AI · Delivery Finance Platforms · Research**

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://protfolio-chi-two.vercel.app/) [![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ved-vivek-talmaley-ba51a328b) [![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:vedwork21@gmail.com) [![ORCID](https://img.shields.io/badge/ORCID-A6CE39?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0009-0006-6444-9446)

---

## Who I Am

**B.Tech CSE (Final Year) @ SRM Institute of Science and Technology** | CGPA 8.33/10

I design AI systems from first principles: multimodal vision-language models, multi-agent legal pipelines, hallucination evaluation frameworks, quantitative finance platforms, and production ETL systems. I ship working software, not research papers.

**Current Focus:** Financial intelligence platforms (HSBC QuantumLens), agentic AI workflows, geospatial ML, patent processing (SESPM Phase 2)

---

## Projects at a Glance

| Project | Domain | Architecture | Key Metrics | Status |
|---------|--------|--------------|-------------|--------|
| **X-Fin** | Delivery Finance | FastAPI + Streamlit + PostgreSQL | 5 engines, 20+ KPIs, Monte Carlo | Production |
| **QuantumLens** | Financial Intelligence | Supabase + RAG + Dictionary ETL | One-record-per-metric, P&L automation | Shipped |
| **TerraSight** | Geospatial AI | SpectralViT + LoRA + FastAPI | 68.4% VQA, R²=0.951 NDVI, Live demo | Production |
| **LexAI** | Legal AI | LangGraph + Aurora PostgreSQL | 7-agent pipeline, 24h build, Top 60/22k | Hackathon Win |
| **HalluciNet** | LLM Validation | Gemini 1.5 + Express.js + SQLite | Structured audit logs, critic model | Deployed |

---

## Featured Deep Dives

### 🏦 X-Fin: Enterprise Delivery Finance Operating System
**What it does:** Transforms consulting delivery data (billable hours, project pipelines, staffing actuals) into risk-adjusted revenue forecasts and executive decision intelligence.

**Architecture Stack:**
- **Ingest:** FastAPI REST endpoints for actuals, budgets, pipeline, staffing data
- **Processing:** 5 deterministic engines + 5,000-iteration Monte Carlo + risk/staffing validators
- **Output:** Streamlit executive dashboard + API decision surfaces + natural language briefings

**Technical Highlights:**
- **Forecast Engine:** Deterministic 5-step model with 5% execution risk haircut
- **Monte Carlo:** 5,000 iterations → P10/P50/P90 confidence intervals + Value-at-Risk
- **Risk Engines:** Headroom, margin erosion, portfolio concentration, leakage detection
- **Staffing Engine:** Capacity checks, utilization tracking, data quality guardrails
- **Intelligence Layer:** 20+ derived metrics, 9 diagnostic insights, 10 action triggers

**Repository:** [VED-VIVEK-TALMALEY/x-fin](https://github.com/VED-VIVEK-TALMALEY/x-fin)  
**Docs:** Architecture.md, API.md, DATA_MODEL.md, FORECAST_ENGINE.md  
**Test Coverage:** 9 test modules (forecast, Monte Carlo, variance, scenario, staffing, decisions, risk, confidence, mongo integration)

---

### 💰 QuantumLens: HSBC Financial Intelligence Platform
**What it does:** Automates extraction of financial metrics from HSBC's earnings workbooks into a queryable warehouse with RAG-powered copilot.

**Problem Solved:**
- Manual extraction from 20+ sheet workbooks → dictionary-first KPI matching
- Financial analysts spending hours cross-referencing → RAG agent retrieves exact metrics
- No normalized data model → one-record-per-metric Supabase design

**Technical Stack:**
- **Ingestion:** Python ETL pipeline + dictionary-based alias matching (NII, Banking NII → nii)
- **Storage:** Supabase + pgvector for semantic search
- **Retrieval:** RAG layer with density-scored sheet skipping
- **Frontend:** Executive copilot with natural language queries

**Key Results:**
- ✅ One-record-per-metric warehouse design (normalized + queryable)
- ✅ Dictionary-first matching eliminates manual lookup overhead
- ✅ Density-scored sheet ranking (high-signal sheets prioritized)
- ✅ Live copilot for "what was HSBC's NII in Q2 2024?"

**Reference:** CFA-aligned methodology, HSBC public disclosures benchmarked

---

### 🛰️ TerraSight: Multimodal Geospatial AI Framework
**What it does:** Ask satellite imagery questions in plain English. Custom SpectralViT handles 13-band multispectral Earth Observation data.

**Architecture:**
- **Vision Backbone:** SpectralViT fine-tuned on 13-band multispectral satellite data
- **Language Head:** GPT-2 + LoRA for natural language question-answering
- **Inference:** FastAPI backend + React/Express frontend + MapLibre GL for geospatial viz

**Performance:**
- 🎯 **VQA Accuracy:** 68.4% (multimodal question-answering on satellite imagery)
- 🎯 **NDVI Regression:** R²=0.951 (normalized difference vegetation index prediction)
- 🎯 **Loss Reduction:** 41.3% improvement over 7 epochs
- 🎯 **Data:** ISRO Cartosat-2 multispectral imagery

**Live Demo:** [terrasight.streamlit.app](https://terrasight.streamlit.app)  
**Paper:** First-author submission, EAI CloudComp 2026  
**Repository:** [VED-VIVEK-TALMALEY/TerraSight](https://github.com/VED-VIVEK-TALMALEY/TerraSight)

---

### ⚖️ LexAI: Multi-Agent Legal Document Processing Pipeline
**What it does:** 7-agent LangGraph pipeline for automated legal document intake, classification, risk assessment, and audit trails.

**Agents (Spec):**
1. **Intake Agent** → Document parsing + metadata extraction
2. **Classification Agent** → Contract type, jurisdiction, risk class
3. **Precedent Agent** → Semantic search against legal knowledge base
4. **Risk Agent** → Contract risk assessment + flagged clauses
5. **Summary Agent** → Executive summary generation
6. **Audit Agent** → State graph validation + decision logging
7. **Feedback Agent** → Continuous improvement from analyst corrections

**Architecture:**
- **Graph Engine:** LangGraph with Pydantic-validated state mutations
- **Database:** Aurora PostgreSQL for precedent storage + decision history
- **Built:** 24 hours in Deloitte Hacksplosion 2026

**Achievement:**
- 🏆 **Top 60 / 22,000+ teams** nationally
- 🏆 Team Lead & Sole Architect
- ✅ Built on Deloitte's GenW.AI infrastructure

**Repository:** [VED-VIVEK-TALMALEY/LexAI](https://github.com/VED-VIVEK-TALMALEY/LexAI)

---

### 🧠 HalluciNet: LLM Hallucination Detection Framework
**What it does:** Uses Gemini 1.5 as an independent critic model to detect and score hallucinations against retrieved ground truth.

**Design:**
- **Checker Model:** Gemini 1.5 Flash (cost-optimized critic)
- **Retrieval:** Ground truth documents from knowledge base
- **Scoring:** Structured hallucination severity (0-10 scale)
- **Audit Trail:** SQLite ledger of all checks + corrections

**Stack:** Express.js + SQLite + Gemini API  
**Repository:** [VED-VIVEK-TALMALEY/HalluciNet](https://github.com/VED-VIVEK-TALMALEY/HalluciNet)

---

## Technical Arsenal

### Languages & Core
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=cplusplus&logoColor=white)

### AI / ML Stack
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square)
![LangChain](https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square)
![RAG](https://img.shields.io/badge/RAG_Pipelines-6E56CF?style=flat-square)
![Vector_DB](https://img.shields.io/badge/pgvector-6E56CF?style=flat-square)
![Gemini_API](https://img.shields.io/badge/Gemini-8E75B2?style=flat-square&logo=googlegemini&logoColor=white)
![OpenAI_API](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)

### Backend & Data
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=flat-square&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=flat-square&logo=supabase&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)

### Frontend & Viz
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat-square&logo=plotly&logoColor=white)
![MapLibre_GL](https://img.shields.io/badge/MapLibre_GL-396CB2?style=flat-square)

### DevOps & Tools
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)
![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=postman&logoColor=white)

---

## Research, IP & Achievements

| Achievement | Details | Date |
|---|---|---|
| **Deloitte Hacksplosion 2026** | Top 60 / 22,000+ teams · Team Lead · Sole Architect (LexAI) | 2026 |
| **EAI CloudComp 2026** | First-author paper · TerraSight (SpectralViT + LoRA on ISRO data) | Submitted |
| **Patent Processing** | SESPM (Self-Evolving Spatiotemporal Pattern Matrix) Phase 2 | In Progress |
| **SAP Certification** | Generative AI Developer | Apr 2026 |
| **GenW.AI Certification** | AI-Architect by Deloitte | 2026 |

---

## Quick Start: Running the Projects

### X-Fin (Delivery Finance)
```bash
git clone https://github.com/VED-VIVEK-TALMALEY/x-fin.git
cd x-fin
pip install -r requirements.txt
python app/main.py              # FastAPI on :8000
streamlit run dashboard/app.py  # UI on :8501
```

### TerraSight (Geospatial AI)
```bash
git clone https://github.com/VED-VIVEK-TALMALEY/TerraSight.git
cd TerraSight
pip install -r requirements.txt
streamlit run app.py  # Live demo
```

### LexAI (Legal AI)
```bash
git clone https://github.com/VED-VIVEK-TALMALEY/LexAI.git
cd LexAI
pip install -r requirements.txt
python main.py  # Run agent pipeline
```

---

## GitHub Activity & Contributions

**Total Repositories:** 15+  
**Primary Focus:** AI systems, financial platforms, geospatial ML  
**Code Style:** Type-hinted Python, RESTful APIs, documented architectures  
**Testing:** Unit tests, integration tests, edge case coverage

---

## Let's Connect

**Working on:**
- LLM system design & agent orchestration
- Quantitative finance & portfolio optimization
- Geospatial ML & satellite imagery
- Multi-agent reasoning frameworks

**Open to:** Internships, research collaborations, startup founding, consulting roles

**Contact:**  
📧 [vedwork21@gmail.com](mailto:vedwork21@gmail.com)  
🔗 [LinkedIn](https://linkedin.com/in/ved-vivek-talmaley-ba51a328b)  
🌐 [Portfolio](https://protfolio-chi-two.vercel.app/)  
📊 [ORCID](https://orcid.org/0009-0006-6444-9446)
