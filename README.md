[![LeetCode](https://leetcard.jacoblin.cool/ved_talmaley?theme=dark&font=fira_code&ext=heatmap&border=0&radius=10)](https://leetcode.com/u/ved_talmaley/)

<div align="center">

```
██╗   ██╗███████╗██████╗     ██╗   ██╗██╗██╗   ██╗███████╗██╗  ██╗
██║   ██║██╔════╝██╔══██╗    ██║   ██║██║██║   ██║██╔════╝██║ ██╔╝
██║   ██║█████╗  ██║  ██║    ██║   ██║██║██║   ██║█████╗  █████╔╝ 
╚██╗ ██╔╝██╔══╝  ██║  ██║    ╚██╗ ██╔╝██║╚██╗ ██╔╝██╔══╝  ██╔═██╗ 
 ╚████╔╝ ███████╗██████╔╝     ╚████╔╝ ██║ ╚████╔╝ ███████╗██║  ██╗
  ╚═══╝  ╚══════╝╚═════╝       ╚═══╝  ╚═╝  ╚═══╝  ╚══════╝╚═╝  ╚═╝
```

### I build AI systems that actually ship.
**Multi-Agent Pipelines · LLM Engineering · Geospatial AI · Research**

[![Portfolio](https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://protfolio-chi-two.vercel.app/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/ved-vivek-talmaley-ba51a328b)
[![Email](https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:vedwork21@gmail.com)
[![ORCID](https://img.shields.io/badge/ORCID-A6CE39?style=for-the-badge&logo=orcid&logoColor=white)](https://orcid.org/0009-0006-6444-9446)

</div>

---

## ⚡ Who Am I

Third-year **B.Tech CS @ SRM Institute of Science and Technology** (CGPA: 8.33/10).

I don't just implement papers — I design systems from scratch. My work spans multimodal vision-language models trained on satellite imagery, 7-agent legal AI pipelines deployed in production at a national hackathon, LLM hallucination evaluation frameworks, and original research in spatiotemporal financial modeling.

**What I'm doing right now:**
- 🛰️ SESPM — original research: Self-Evolving Spatiotemporal Pattern Matrix for financial time series (Phase 1 architecture complete, 18 equation groups)
- 📄 EAI CloudComp 2026 — first-author paper submitted (TerraSight)
- ⚖️ Patent pending — co-inventor on TerraSight environmental analytics system
- 🏆 Deloitte Hacksplosion 2026 — Top 60 / 22,000+ teams nationally (Team Lead)

---

## 🚀 Featured Projects

### 🌍 [TerraSight — Multimodal Geospatial AI](https://github.com/VED-VIVEK-TALMALEY/TerraSight)
> *Ask satellite imagery questions in plain English. Get domain-aware answers.*

**The Problem:** ISRO's open-source GPT models had no multimodal vision capability for Earth Observation data. Standard ViTs can't handle multispectral input (13 bands). GPT-2 can't interpret SAR imagery.

**Why This Stack:**
| Choice | Why |
|---|---|
| SpectralViT (custom) | Standard ViT patch embeddings assume RGB. EO data has 13+ bands with non-uniform spectral relationships — needed band-aware cross-attention from scratch |
| GPT-2 + LoRA (not GPT-4) | Controllable fine-tuning on domain-specific EO instruction data. LoRA keeps trainable params < 1% of total — runnable on academic hardware |
| FastAPI + Express.js dual backend | ML inference (Python) and API orchestration (Node.js) are different performance profiles. Separation lets them scale independently |
| MapLibre GL (not Google Maps) | Open-source, supports 3D terrain, and polygon-draw capability is first-class — critical for the area-selection research workflow |

**Architecture:**
```
Multispectral Input (13 bands, 512×512)
        ↓
  Spectral Attention + Patch Embedding   ← band-aware, not RGB-assumed
        ↓
  SpectralViT Encoder                    ← vision transformer with spectral adapters
        ↓
  Projection Layer                       ← maps vision → language space
        ↓
  GPT-2 + LoRA Adapters                  ← PEFT fine-tuned, ~1% params trained
        ↓
  Text Response (NDVI, land cover, disaster response)
```

**Numbers that matter:**
- 📉 **41.3% training loss reduction** over 7 epochs
- 🌿 **NDVI R² = 0.951** (near-perfect vegetation index regression)
- ✅ **68.4% VQA accuracy** on held-out EO instruction data
- 🔬 **3-stage curriculum**: pretraining → instruction tuning → ISRO domain specialization

**Live Demo:** [terrasight.streamlit.app](https://terrasight.streamlit.app) — draw a polygon over any region on the 3D map, get an AI analysis in real time.

**Complexity Note:** The core bottleneck is the projection layer between vision and language spaces. Vocabulary mismatch between a 768-dim ViT embedding and GPT-2's token space is solved with a learned linear/MLP bridge — trained in Stage 1 with all other weights frozen. Class imbalance across 10 land cover types is addressed with inverse-frequency weighted sampling, not naive oversampling.

---

### ⚖️ [LexAI — Multi-Agent Legal AI Platform](https://github.com/VED-VIVEK-TALMALEY/LexAI) *(Deloitte Hacksplosion 2026 — Top 60 / 22,000+ Teams)*
> *7-agent pipeline. Production PostgreSQL backend. Live at a Deloitte URL.*

**The Problem:** Legal document workflows are manual, slow, and error-prone at scale. Deloitte's challenge: build an AI platform on their GenW.AI infrastructure within 24 hours.

**Why This Stack:**
| Choice | Why |
|---|---|
| LangGraph (not LangChain sequential) | Legal case processing has conditional routing — a contract dispute needs different agents than a compliance case. LangGraph's stateful graph enables conditional branching, not linear chains |
| Aurora PostgreSQL (not a vector DB) | Structured legal data (cases, precedents, acts_cited, legal_issues) fits relational schemas better than embedding stores. JOINs across case metadata are faster and more interpretable |
| 7-agent decomposition | Intake → Classification → Precedent Retrieval → Issue Extraction → Risk Assessment → Summary Generation → Audit Logging. Modularity meant each agent could be swapped without breaking the pipeline |

**Architecture:**
```
Document Ingestion (OCR)
        ↓
[Intake Agent] → [Classification Agent] → [Precedent Retrieval Agent]
                          ↓
              [Issue Extraction Agent]
                          ↓
              [Risk Assessment Agent]
                          ↓
              [Summary Generation Agent]
                          ↓
              [Audit Logging Agent] → Aurora PostgreSQL
                          ↓
              App Maker Dashboard (KPI cards + RealmAI Q&A embed)
```

**Complexity Note:** The hard engineering problem wasn't the agents — it was state management across the graph. LangGraph's StateGraph requires explicit schema definition for every key that flows between nodes. With 7 agents sharing a 40+ key state object (case metadata, confidence scores, retrieved precedents, intermediate summaries), schema drift between agent outputs broke the pipeline twice before proper Pydantic validation was added at every edge.

---

### 🧠 [Brain Tumour Detection CNN](https://github.com/VED-VIVEK-TALMALEY/CNN-BRAIN-TUMOUR-DETECTION-)
> *MRI classification with production deployment — 85–95% validation accuracy.*

**Why This Stack:**
| Choice | Why |
|---|---|
| Custom CNN (not ResNet transfer learning) | Transfer learning on ImageNet features ≠ MRI features. Grayscale brain scans have fundamentally different texture statistics. Training from scratch on domain-specific augmentation was the right call |
| Flask + glass morphism UI | Medical tools need reassuring, clinical aesthetics — not generic dashboards. Glass morphism on dark background reduces cognitive load for the prediction output |
| Data augmentation (rotation, shear, zoom, flip) | Brain tumours appear at arbitrary orientations and scales in MRI. Augmentation is domain-motivated, not boilerplate |

```
Input: MRI scan (150×150 px)
        ↓
Conv2D(32) → MaxPool → Conv2D(64) → MaxPool
        ↓
Conv2D(128) → MaxPool → Conv2D(256) → MaxPool
        ↓
Flatten → Dense(512, ReLU) → Dropout(0.5) → Dense(1, Sigmoid)
        ↓
Binary output: Tumour / No Tumour + confidence score
```

**Complexity Note:** The 0.5 dropout layer before output is deliberate — medical inference tools must not be overconfident. The model reports probability, not just class label, specifically to communicate uncertainty to the end user.

**Live Demo:** [braintumoro.streamlit.app](https://braintumoro.streamlit.app)

---

### 🔍 [HalluciNet — LLM Validation Framework](https://github.com/VED-VIVEK-TALMALEY/HalluciNet)
> *Automated hallucination detection using Gemini 1.5 as the evaluator.*

**The insight:** You can't reliably detect hallucinations using the same model that generated the response. HalluciNet uses Gemini 1.5 as a critic model, comparing claims in LLM outputs against retrieved ground truth, with structured scoring and audit logging.

**Stack:** Express.js · SQLite · Gemini API · reproducible scoring pipelines

---

### 📊 [Ministry of Finance NLP Analytics Pipeline](https://github.com/VED-VIVEK-TALMALEY/Ministry-Finance-NLP)
> *35-year longitudinal regulatory signal extraction from government reports.*

End-to-end pipeline: automated ingestion of Ministry of Finance documents → NLP-based macroeconomic signal classification → structured reporting. The EWS-4 early warning framework flags regulatory stress signals across four indicator dimensions.

---

## 🛠️ Technical Arsenal

```python
stack = {
    "AI/ML":        ["PyTorch", "HuggingFace", "LangGraph", "LangChain", "PEFT/LoRA",
                     "RAG Pipelines", "Vector Retrieval", "Gemini API", "OpenAI API"],
    "Backend":      ["FastAPI", "Express.js", "Flask", "PostgreSQL", "SQLite", "REST APIs"],
    "Frontend":     ["React", "TypeScript", "Vite", "Streamlit", "MapLibre GL"],
    "Data":         ["Pandas", "NumPy", "yFinance", "scikit-learn", "Matplotlib"],
    "DevOps":       ["Docker", "Git", "Postman"],
    "Languages":    ["Python", "SQL", "JavaScript", "C++"],
    "Certified":    ["SAP Generative AI Developer (Apr 2026)"]
}
```

---

## 📈 Research

### SESPM — Self-Evolving Spatiotemporal Pattern Matrix *(In Progress)*
Original research applying spatiotemporal ML to financial time series. Phase 1 architecture complete (18 equation groups in LaTeX). Phase 2 scoped: SESPM-ESG integrating satellite-derived NDVI signals with financial indicators via the TerraSight pipeline.

**EAI CloudComp 2026** — First-author paper submitted (TerraSight multimodal EO system).

**Patent Filing** — Co-inventor, environmental analytics system (TerraSight).

---

## 🏆 Achievements

| | |
|---|---|
| 🥇 **Deloitte Hacksplosion 2026** | Top 60 / 22,000+ teams nationally — Team Lead & Sole Architect |
| 📄 **EAI CloudComp 2026** | First-author research paper submission |
| 🔬 **Patent Pending** | Co-inventor, TerraSight environmental analytics system |
| 🎓 **SAP Certified** | Generative AI Developer — Apr 2026 |

---

## 📊 GitHub Stats

<div align="center">

![Ved's GitHub Stats](https://github-readme-stats.vercel.app/api?username=VED-VIVEK-TALMALEY&theme=dark&hide_border=false&include_all_commits=false&count_private=false)
![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=VED-VIVEK-TALMALEY&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

</div>

---

## 📬 Let's Talk

If you're working on LLM systems, agentic AI, geospatial ML, or original research in quantitative finance — I'm interested.

**vedwork21@gmail.com** | [LinkedIn](https://linkedin.com/in/ved-vivek-talmaley-ba51a328b) | [Portfolio](https://protfolio-chi-two.vercel.app/)

---

<div align="center">
<sub>SRM Institute of Science and Technology · B.Tech CSE · Chennai, India · 2023–2027</sub>
</div>




<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
