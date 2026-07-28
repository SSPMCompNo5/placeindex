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
├── README.md                                # Primary project overview (this file)
├── SOFTWARE_REQUIREMENTS_SPECIFICATION.md   # IEEE 830 compliant Software Requirement Specification (SRS)
├── PROJECT_REFERENCE.md                     # Master reference document — concept, architecture, tech stack & paper framework
├── RESEARCH_PAPERS.md                       # 33 curated research papers, literature survey guide & 6 novel project innovations
└── REALTIME_DATA_SOURCES.md                 # Master directory of 40+ APIs (OpenAQ, Overpass OSM, PyTrends, ISRO Bhuvan, RBI DBIE) & code
```

---

## 🛠️ Tech Stack Architecture

- **Frontend**: Next.js (React), TypeScript, D3.js (stock charts), Mapbox GL JS (heat maps), Framer Motion
- **Backend & APIs**: FastAPI (Python), Pydantic, Celery + Redis, Nginx
- **Database & Storage**: PostgreSQL + PostGIS (geo), TimescaleDB (time-series scores), Elasticsearch (full-text search)
- **AI & ML Pipeline**: LangChain / CrewAI agents, Gemini / GPT-4o, Prophet, XGBoost, PyTorch LSTM, FinBERT NLP
- **Data Ingestion**: Apache Airflow, Scrapy, Playwright, Overpass API (OSM), OpenAQ API, PyTrends

---

## 📚 Project Reference Guides & Specifications

This repository contains comprehensive blueprints and technical specifications:

1. 📋 **[SOFTWARE_REQUIREMENTS_SPECIFICATION.md](SOFTWARE_REQUIREMENTS_SPECIFICATION.md)** — Formal IEEE Std 830-1998 Software Requirement Specification (SRS) with functional modules FR-1 to FR-8, non-functional requirements NFR-1 to NFR-14, DFD Level 0/1, and ER schema.
2. 📖 **[PROJECT_REFERENCE.md](PROJECT_REFERENCE.md)** — Master technical blueprint covering product concept, 5-pillar mathematical model, 10 data categories, 5-agent AI swarm, system tech stack, and academic framework.
3. 📚 **[RESEARCH_PAPERS.md](RESEARCH_PAPERS.md)** — Academic references featuring 33 literature sources, paper outline, target IEEE/ACM conferences, and 6 novel contributions.
4. 🌐 **[REALTIME_DATA_SOURCES.md](REALTIME_DATA_SOURCES.md)** — Complete directory of 40+ open data APIs, government registries (MahaRERA, Ready Reckoner Rates, ISRO Bhuvan), scrapers, and python connector scripts.

---

## 👨‍💻 Team & License

- **Project Group**: SSPMCompNo5 (`sspmprojectgroup@gmail.com`)
- **Institution**: Final Year Computer Engineering Project
- **Status**: Active Development & Research Phase
