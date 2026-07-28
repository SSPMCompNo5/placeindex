# PlaceIndex — Real Estate Area Investment Index & AI Swarm Platform

> **A Strategic Planning, Multi-Agent AI & Spatial Scoring Engine for Real Estate Micro-Markets**
> *Treating real estate localities like stocks — giving every neighborhood a trackable investment score and actionable Buy / Hold / Review / Avoid signals.*

---

## 📌 Project Overview

**PlaceIndex** is an AI-powered real estate market intelligence platform built to solve a fundamental problem in real estate: while traditional platforms evaluate *individual properties*, PlaceIndex evaluates **areas as investable assets**.

Modeled after equity stock screeners (e.g. Zerodha, Groww, Bloomberg), PlaceIndex combines **10 ground-level data categories** across livability, infrastructure, price momentum, and sentiment into a standardized **PlaceIndex Score (0–100)** and generates actionable investment stances (**Buy 🟢 / Hold 🟡 / Review 🟠 / Avoid 🔴**).

---

## 🌟 Key Features & Innovations

- 🏢 **Locality-as-an-Asset Paradigm**: Evaluates micro-markets (e.g. Bandra West, Powai, Juhu, Worli, Lower Parel) with stock-style trend charts, indicators, and comparison tools.
- 📐 **5-Pillar Composite Scoring Formula**: Based on OECD composite index standards, combining:
  - **P1 — Price Momentum (25%)**: 5-Year Price CAGR, resale vs. launch gap
  - **P2 — Rental & Income (20%)**: Rental yield %, rent growth YoY, occupancy rates
  - **P3 — Liquidity & Demand (20%)**: Monthly transaction volumes, time-on-market, inventory absorption
  - **P4 — Infrastructure & Development (20%)**: Metro/highway progress, RERA launches, commercial office density
  - **P5 — Livability & Growth Signals (15%)**: Crime trends, school/hospital density, AQI, green cover, news sentiment
- 🤖 **Multi-AI Agent Swarm Architecture**: Specialized AI agents with live internet access collaborating via an Orchestrator:
  - **Research Agent 🔍**: Monitors web news, infra announcements, policy updates
  - **Data Agent 📊**: Fetches pricing, rental listings, government APIs, and land registries
  - **Prediction Agent 🤖**: Runs hybrid ML models (Prophet + XGBoost + LSTM) for 6/12/24 month score forecasts
  - **Signal Agent 🚦**: Classifies investment stances with confidence intervals & explanatory rationale
  - **Orchestrator Agent 🎯**: Coordinates agent workflows and resolves data conflicts
- 🗺️ **Hierarchical Spatial Indexing**:
  - `Level 1 (Micro)`: Bandra West, Juhu, Powai $\rightarrow$
  - `Level 2 (City)`: Volume-weighted Mumbai City Index $\rightarrow$
  - `Level 3 (State)`: Maharashtra State Index $\rightarrow$
  - `Level 4 (National)`: India Real Estate Index
- 🔬 **Academic & Research Worthy**: Designed for a final-year college project with backtesting, ablation study capabilities, and 33 curated academic literature references.

---

## 📂 Repository File Structure

```
placeindex/
│
├── README.md                      # Primary project overview (this file)
├── PROJECT_REFERENCE.md           # Master reference document — core concept, architecture, tech stack & paper framework
├── RESEARCH_PAPERS.md             # 33 curated research papers, literature survey guide & 6 novel project innovations
├── REALTIME_DATA_SOURCES.md       # Master directory of 40+ APIs (OpenAQ, Overpass OSM, PyTrends, ISRO Bhuvan, RBI DBIE) & code
└── prototype_scoring_engine.py    # Working Python prototype implementing Z-score normalization, pillar math & city roll-up
```

---

## 🛠️ Tech Stack Architecture

- **Frontend**: Next.js (React), TypeScript, D3.js (stock charts), Mapbox GL JS (heat maps), Framer Motion
- **Backend & APIs**: FastAPI (Python), Pydantic, Celery + Redis, Nginx
- **Database & Storage**: PostgreSQL + PostGIS (geo), TimescaleDB (time-series scores), Elasticsearch (full-text search)
- **AI & ML Pipeline**: LangChain / CrewAI agents, Gemini / GPT-4o, Prophet, XGBoost, PyTorch LSTM, FinBERT NLP
- **Data Ingestion**: Apache Airflow, Scrapy, Playwright, Overpass API (OSM), OpenAQ API, PyTrends

---

## 🚀 Running the Prototype Scoring Engine

Run the standalone Python prototype script to see the 5-Pillar Scoring Engine and Volume-Weighted City Roll-Up in action:

### Prerequisites
- Python 3.9 or higher

### Command
```bash
# Clone the repository
git clone https://github.com/SSPMCompNo5/placeindex.git
cd placeindex

# Run the scoring engine script
python prototype_scoring_engine.py
```

### Sample Output
```
======================================================================
 🏙️  PLACEINDEX — REAL ESTATE AREA INVESTMENT INDEX PROTOTYPE ENGINE
======================================================================

📍 CITY SUMMARY: MUMBAI INDEX
   City Score: 74.8 / 100  |  Signal: HOLD
   Total Volume: 705 transactions/mo across 6 micro-markets

----------------------------------------------------------------------
Rank  Micro-Market    Score    Signal   P1(Price)  P4(Infra)  P5(Live)  
----------------------------------------------------------------------
1     Powai           84.6     BUY      76.7       68.6       77.6      
2     Bandra West     82.5     BUY      80.3       74.5       69.1      
3     Lower Parel     66.6     HOLD     57.2       68.2       44.2      
4     Worli           62.3     HOLD     44.8       62.7       49.0      
5     Juhu            59.2     REVIEW   36.8       26.1       65.5      
6     Mira Road       27.4     AVOID    0.0        21.7       2.4       
----------------------------------------------------------------------

✅ Results exported successfully to prototype_scores_output.json
```

---

## 📄 Key Reference Documents

1. 📖 **[PROJECT_REFERENCE.md](PROJECT_REFERENCE.md)** — Comprehensive project blueprint.
2. 📚 **[RESEARCH_PAPERS.md](RESEARCH_PAPERS.md)** — Academic references, literature review, and research methodology.
3. 🌐 **[REALTIME_DATA_SOURCES.md](REALTIME_DATA_SOURCES.md)** — Free APIs, scrapers, ISRO Bhuvan GIS, RBI DBIE, and python scripts.

---

## 👨‍💻 Team & License

- **Project Group**: SSPMCompNo5 (`sspmprojectgroup@gmail.com`)
- **Institution**: Final Year Computer Engineering Project
- **Status**: Active Development & Research Phase
