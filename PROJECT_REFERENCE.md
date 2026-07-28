# PlaceIndex — Real Estate Area Investment Index Dashboard

> **Status:** Concept / Strategic Planning Phase
> **Last Updated:** 2026-07-28

---

## 1. Core Concept

Build a platform that treats **real estate localities** (neighborhoods, areas, micro-markets) the way the **stock market treats companies** — giving each area a trackable **"investment score"** so people can compare, rank, and receive **Buy / Hold / Review / Avoid**-style signals on *where* to invest in property, not just *which* property.

### The Key Shift

| Traditional Real Estate | PlaceIndex Approach |
|---|---|
| Evaluate individual properties | Evaluate **areas as investable assets** |
| Gut-feel + broker advice | Data-driven scoring + signals |
| Hard to compare across localities | Stock-screener-style comparison tools |
| No standardized "index" per area | Each locality gets a trackable score over time |

---

## 2. Scoring Model — Expanded with Realistic Data Layers

The score for each area is built from **real, ground-level data** — not just price trends. The AI agents collect data across **10 categories** covering everything from crime rates to school quality to air pollution. These feed into **5 scoring pillars** that produce the final PlaceIndex Score.

### 2.1 The 5 Scoring Pillars (Summary)

| Pillar | Weight | What Feeds Into It |
|---|---|---|
| **P1 — Price Momentum** | 0.25 | Price CAGR, price-per-sq-ft trends, new launch vs. resale gap |
| **P2 — Rental & Income** | 0.20 | Rental yield, rent growth rate, vacancy rates |
| **P3 — Liquidity & Demand** | 0.20 | Transaction volume, time-on-market, inventory absorption |
| **P4 — Infrastructure & Development** | 0.20 | Infra projects, construction activity, government investment |
| **P5 — Livability & Growth Signals** | 0.15 | Crime, schools, hospitals, environment, jobs, demographics |

### 2.2 The 10 Realistic Data Categories

Every data point below is something the **AI agents actively search for and track** via internet access, APIs, and public databases.

---

#### 📚 Category 1: Education & Schools

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Number of schools in the area | Family-friendliness, residential demand driver | Google Maps API, school directories |
| School quality ratings | Premium locality indicator | GreatSchools-style ratings, board results |
| Proximity to top-rated schools | Price premium zone identifier | Distance calculations from listings |
| Colleges & universities nearby | Student rental demand, young workforce | UGC / AICTE databases |
| Coaching center / tuition density | Education hub signal | Local listing data |

---

#### 🚔 Category 2: Crime & Safety

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Crime rate (per 1,000 residents) | Safety — direct impact on property values | NCRB (National Crime Records Bureau) |
| Crime trend (increasing/decreasing) | Area improving or declining | Year-over-year NCRB data |
| Type of crimes (petty vs. violent) | Severity of safety concern | FIR data, police station reports |
| Police station density | Response capability | Google Maps, state police portals |
| Gated community / security adoption | Market response to safety needs | Listing data, society registrations |

---

#### 🏥 Category 3: Healthcare & Hospitals

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Number of hospitals & clinics | Basic livability infrastructure | Google Maps API, NHP (National Health Portal) |
| Multi-specialty hospital presence | Premium healthcare access → premium locality | Hospital directories |
| Hospital beds per 1,000 residents | Healthcare capacity | Government health surveys |
| Pharmacy & diagnostic lab density | Day-to-day healthcare convenience | Local listing data |
| Ambulance response coverage | Emergency infrastructure quality | State health department data |

---

#### 🏗️ Category 4: Development & Construction Activity

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| New RERA-registered projects | Active development = growth signal | State RERA portals (MahaRERA, etc.) |
| Under-construction projects count | Future supply pipeline | RERA + listing site data |
| Commercial vs. residential ratio | Economic diversification of area | Land use records, listing data |
| Redevelopment projects (SRA/cluster) | Urban renewal signal (esp. Mumbai) | BMC/municipal records, news |
| Completion rate of past projects | Developer reliability in the area | RERA compliance data |
| Building permits issued (trend) | Forward-looking development indicator | Municipal corporation data |

---

#### 🚇 Category 5: Infrastructure & Connectivity

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Metro station proximity & upcoming lines | Single biggest price appreciation driver | MMRDA, DMRC project trackers |
| Highway / expressway connectivity | Intercity access, commercial viability | NHAI project data |
| Railway station proximity | Daily commuter convenience | Indian Railways data |
| Airport distance | Premium for business travelers, NRIs | Distance calculations |
| Road quality & width | Day-to-day livability, traffic flow | Municipal data, Google Street View |
| Upcoming infra projects (planned) | Future appreciation catalyst | Government gazette, news tracking |
| Water supply reliability | Basic infrastructure quality | Municipal utility reports |
| Power supply stability | Infrastructure maturity | Discom data, consumer forums |

---

#### 🏢 Category 6: Commercial & Economic Activity

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| IT parks & tech offices | White-collar job density → rental demand | News, company websites, STPI data |
| Co-working spaces | Startup / freelancer ecosystem | Listing data (WeWork, 91springboard etc.) |
| Shopping malls & retail | Consumer spending power | Google Maps, retail directories |
| New company office openings | Job creation signal | News tracking, commercial lease data |
| Bank branch / ATM density | Financial services penetration | RBI data, Google Maps |
| Restaurant & café density | Lifestyle quotient, footfall indicator | Zomato / Swiggy API |

---

#### 🌳 Category 7: Environment & Quality of Life

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Air Quality Index (AQI) | Health & livability factor | CPCB / SAFAR real-time data |
| Green cover / park density | Premium lifestyle indicator | Satellite imagery, municipal data |
| Noise levels | Residential comfort | CPCB noise monitoring |
| Flood risk / waterlogging history | Seasonal risk, insurance cost | IMD data, BMC flood maps, news |
| Waste management quality | Civic infrastructure maturity | Swachh Bharat data, municipal reports |
| Proximity to water bodies | Aesthetic value vs. flood risk | Geographic data |

---

#### 👥 Category 8: Demographics & Population

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Population density | Demand pressure vs. congestion | Census data |
| Population growth rate | Demand trajectory | Census + voter roll trends |
| Average household income | Purchasing power of area | NSSO surveys, tax data proxies |
| Age distribution | Young = growth; aging = stable | Census data |
| Migration inflow/outflow | Area gaining or losing people | Census, electoral roll changes |
| Literacy rate | Socioeconomic indicator | Census data |

---

#### 💰 Category 9: Real Estate Market Data

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Current price per sq. ft. | Baseline price level | 99acres, MagicBricks, Housing.com |
| 5-year price CAGR | Historical appreciation trend | Registration data, listing archives |
| Rental price per sq. ft. | Income potential | Rental listing sites |
| Rental yield (%) | Return on investment metric | Calculated: rent / price |
| Transaction volume (monthly) | Market activity / liquidity | IGR (Inspector General of Registration) |
| Time-on-market (avg. days) | Demand indicator — lower = hotter | Listing site data |
| Inventory count (active listings) | Supply pressure | Listing aggregators |
| New launch vs. resale price gap | Market maturity indicator | RERA + resale listing comparison |
| Stamp duty & registration costs | Total acquisition cost factor | State government rates |

---

#### 📡 Category 10: Emerging & Predictive Signals

| Data Point | What It Tells Us | Example Source |
|---|---|---|
| Google search trends for the area | Demand sentiment proxy | Google Trends API |
| Social media buzz (positive/negative) | Public perception shifts | Twitter/X, Reddit, local forums |
| News sentiment analysis | Media narrative about the area | News APIs + NLP sentiment |
| Government budget allocation | Future infra investment signal | Union & state budget documents |
| Zoning / land use changes | Future development potential | Municipal master plans |
| Smart city project inclusion | Government modernization push | Smart Cities Mission portal |
| SEZ / industrial corridor proximity | Future job creation catalyst | DPIIT data, corridor project portals |

---

### 2.3 How Data Categories Map to Scoring Pillars

```
┌─────────────────────────────────────────────────────────────────┐
│                     10 DATA CATEGORIES                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  Cat 9 (Market Data)  ──────────→  P1: Price Momentum (0.25)   │
│                                                                 │
│  Cat 9 (Rentals)      ──────────→  P2: Rental & Income (0.20)  │
│                                                                 │
│  Cat 9 (Transactions) ──────────→  P3: Liquidity (0.20)        │
│                                                                 │
│  Cat 4 (Development)  ──┐                                       │
│  Cat 5 (Infra)        ──┼──────→  P4: Infrastructure (0.20)    │
│  Cat 6 (Commercial)   ──┘                                       │
│                                                                 │
│  Cat 1 (Education)    ──┐                                       │
│  Cat 2 (Crime)        ──┤                                       │
│  Cat 3 (Healthcare)   ──┼──────→  P5: Livability (0.15)        │
│  Cat 7 (Environment)  ──┤                                       │
│  Cat 8 (Demographics) ──┘                                       │
│                                                                 │
│  Cat 10 (Predictive)  ──────────→  Feeds ALL pillars as         │
│                                    forward-looking modifier      │
└─────────────────────────────────────────────────────────────────┘
```

### 2.4 Why This Data Mix Matters for Prediction

> [!TIP]
> Price data alone tells you **where an area has been**. The other 9 categories tell you **where it's going**.

The AI agents use these data layers to spot **leading indicators** — signals that precede price changes:

| Signal Type | Example | What It Predicts |
|---|---|---|
| **Leading** | Metro line approved for area | Price rise in 1–3 years |
| **Leading** | New IT park announced | Rental demand spike in 6–12 months |
| **Leading** | Crime rate dropping YoY | Area reputation improving → price follows |
| **Leading** | 5 new schools opened | Families moving in → residential demand up |
| **Lagging** | Price already rose 20% | Confirms past momentum (may not continue) |
| **Lagging** | High transaction volume | Confirms current demand (but supply may catch up) |

The Prediction Agent weighs **leading indicators more heavily** than lagging ones when forecasting future scores.



---

## 3. Dashboard & UX Vision

Presented via a dashboard with **stock-market-style UI patterns**:

- **Trend Charts** — Area score plotted over time (like a stock price chart)
- **Heat Maps** — Geographic view of scores across a city/region
- **Comparison Tools** — Side-by-side area comparisons (like a stock screener)
- **Buy / Hold / Review / Avoid Signals** — Actionable investment stance per area
- **Alerts & Watchlists** — Track areas of interest over time

The experience should feel similar to how you'd screen stocks on a trading app (Zerodha, Groww, etc.), but for real estate localities.

---

## 4. Competitive Landscape

Research shows close relatives already exist:

| Product | What It Does | Gap vs. PlaceIndex |
|---|---|---|
| **NHB RESIDEX** | National Housing Bank's residential price index | Government data, no actionable signals, limited UX |
| **PropEquity** | Property analytics & price tracking | Property-level focus, no area-as-asset scoring |
| **NeighborhoodScout** | US-based neighborhood analytics | US-only, no investment index / Buy-Hold-Avoid signals |
| **MagicBricks / 99acres** | Property listings with area insights | Listing platforms, not investment analysis tools |

### Differentiation

> **No existing product delivers the full combination of:**
> 1. A standardized, trackable **investment index per locality**
> 2. **Stock-market-style Buy / Hold / Review / Avoid signals**
> 3. A **screener + comparison UX** modeled on trading apps
>
> This is the core differentiator.

---

## 5. Technical Architecture — Multi-AI Agent System

The engine behind PlaceIndex is a **swarm of specialized AI agents**, each with **live internet access**, working together to research, score, predict, and advise.

### 5.1 Why Multiple Agents?

No single AI can do everything well. Instead, each agent is purpose-built for one job and they collaborate through an orchestrator:

```
┌─────────────────────────────────────────────────────────┐
│                   ORCHESTRATOR AGENT                     │
│          (coordinates all agents, merges outputs)        │
└──────┬──────────┬──────────┬──────────┬─────────────────┘
       │          │          │          │
  ┌────▼───┐ ┌───▼────┐ ┌───▼────┐ ┌───▼─────┐
  │Research│ │  Data  │ │Predict │ │ Signal  │
  │ Agent  │ │ Agent  │ │ Agent  │ │  Agent  │
  └────────┘ └────────┘ └────────┘ └─────────┘
       │          │          │          │
       ▼          ▼          ▼          ▼
   [Internet] [Databases] [ML Models] [User-facing
    Search     & APIs      & Trends    Recommendations]
```

### 5.2 Agent Roles

| Agent | Job | Internet Access | What It Does |
|---|---|---|---|
| **🔍 Research Agent** | Market intelligence | ✅ Full web access | Scours the internet for infrastructure news, government announcements, metro/highway projects, upcoming IT parks, policy changes, real estate news for every area |
| **📊 Data Agent** | Data collection & cleaning | ✅ APIs + scraping | Pulls property prices, rental rates, transaction volumes, price-per-sq-ft from listing sites, government registries, and open datasets |
| **🤖 Prediction Agent** | Forecasting & trends | ❌ Internal models | Takes cleaned data + research signals → runs ML models → predicts future price trends, demand shifts, and score trajectories for each area |
| **🚦 Signal Agent** | Investment recommendations | ❌ Internal logic | Converts predictions + current scores into **Buy / Hold / Review / Avoid** signals with confidence levels and reasoning |
| **🎯 Orchestrator Agent** | Coordination | ✅ As needed | Manages agent workflows, resolves conflicts between agents, ensures data freshness, triggers re-scoring cycles |

### 5.3 How Agents Use Internet Access

The Research and Data agents have **live internet access** to:

- **Track infrastructure developments** — New metro lines, highway expansions, airport projects, SEZ announcements
- **Monitor policy changes** — RERA updates, stamp duty changes, FSI modifications, government housing schemes
- **Scrape real-time market data** — Current listings, asking prices, rental rates, inventory levels
- **Analyze news sentiment** — Media coverage about specific areas (positive/negative buzz)
- **Watch economic indicators** — Job postings in an area, new company offices, commercial leasing activity

> [!IMPORTANT]
> Agents don't just pull data once — they **continuously monitor** the internet so scores and predictions stay current. Think of it like how a stock trading platform has live feeds.

### 5.4 Agent Workflow (Per Scoring Cycle)

```
1. Orchestrator triggers a scoring cycle for an area (e.g., "Bandra West")
2. Research Agent → searches the web for latest news, infra updates, policy changes
3. Data Agent → pulls latest prices, rentals, transactions from APIs/listings
4. Both feed their outputs to the Prediction Agent
5. Prediction Agent → runs forecasting models → outputs trend predictions
6. Signal Agent → combines current score + predictions → generates Buy/Hold/Review/Avoid
7. Orchestrator → validates, resolves conflicts, publishes to dashboard
```

---

## 6. Tech Stack & Data Pipeline

The full system architecture — from raw data ingestion to the user-facing dashboard — broken down by layer.

### 6.1 Architecture Overview

```
┌──────────────────────────────────────────────────────────────────────────┐
│                          USER-FACING LAYER                               │
│  Next.js Dashboard  •  D3.js Charts  •  Mapbox Heat Maps  •  PWA/Mobile │
└───────────────────────────────────┬──────────────────────────────────────┘
                                    │ REST / WebSocket / GraphQL
┌───────────────────────────────────▼──────────────────────────────────────┐
│                            API LAYER                                     │
│          FastAPI (Python)  •  Auth  •  Rate Limiting  •  Cache           │
└───────────────────────────────────┬──────────────────────────────────────┘
                                    │
        ┌───────────────────────────┼───────────────────────────┐
        ▼                           ▼                           ▼
┌───────────────┐  ┌────────────────────────────┐  ┌────────────────────┐
│  SCORING      │  │     AI AGENT LAYER          │  │   ML / PREDICTION  │
│  ENGINE       │  │  LangChain / CrewAI Agents  │  │   LAYER            │
│               │  │  with Internet Access       │  │                    │
│  5-Pillar     │  │                              │  │  Prophet / LSTM    │
│  Calculator   │  │  Research • Data • Predict   │  │  XGBoost / LightGBM│
│               │  │  Signal • Orchestrator       │  │  Sentiment Models  │
└───────┬───────┘  └──────────────┬───────────────┘  └────────┬───────────┘
        │                         │                            │
        └─────────────────────────┼────────────────────────────┘
                                  │
┌─────────────────────────────────▼────────────────────────────────────────┐
│                          DATA LAYER                                      │
│  PostgreSQL + TimescaleDB  •  Redis Cache  •  Elasticsearch  •  S3/GCS  │
└─────────────────────────────────┬────────────────────────────────────────┘
                                  │
┌─────────────────────────────────▼────────────────────────────────────────┐
│                      DATA PIPELINE / INGESTION                           │
│  Apache Airflow  •  Scrapy Spiders  •  API Connectors  •  NLP Parsers  │
└─────────────────────────────────┬────────────────────────────────────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    ▼             ▼             ▼
              [Web Scraping] [Public APIs] [News & Social]
              99acres        NCRB / Census  Google Trends
              MagicBricks    RERA Portals   Twitter/X
              Housing.com    CPCB / IMD     News sites
```

### 6.2 Frontend — Dashboard & Visualization

| Technology | Purpose | Why This Choice |
|---|---|---|
| **Next.js (React)** | Main dashboard framework | SSR for SEO, fast navigation, component-based UI |
| **TypeScript** | Type safety | Prevents runtime bugs in complex data flows |
| **D3.js** | Stock-style trend charts, candlestick charts | Most powerful charting lib — full control over financial-style visuals |
| **Mapbox GL JS** | Interactive heat maps & geo visualization | Best-in-class map rendering, custom styling, smooth zoom levels |
| **Recharts / Tremor** | Simpler charts (bar, pie, comparison) | Quick to build, great defaults for dashboard panels |
| **Framer Motion** | Animations & micro-interactions | Smooth score transitions, chart reveals, hover effects |
| **Socket.io (client)** | Real-time score updates | Push new scores to dashboard without page refresh |

**Key UI Components:**
- Area Score Card (score, signal badge, sparkline trend)
- Full-page Area Profile (all 10 data categories visualized)
- Comparison Tool (side-by-side 2–4 areas)
- Heat Map (city-wide score overlay on map)
- Watchlist & Alerts panel
- Drill-down navigation (India → State → City → Micro-area)

### 6.3 Backend — API & Business Logic

| Technology | Purpose | Why This Choice |
|---|---|---|
| **FastAPI (Python)** | Main API server | Async, fast, auto-generates API docs, Python ML ecosystem |
| **Celery + Redis** | Background task queue | Async scoring jobs, agent task scheduling, rate-limited scraping |
| **Pydantic** | Data validation & schemas | Strict input/output contracts between agents and API |
| **JWT + OAuth 2.0** | Authentication | Secure user sessions, API key management |
| **Nginx** | Reverse proxy + load balancer | Handle traffic, SSL termination, rate limiting |

**Key API Endpoints (Conceptual):**
```
GET  /api/v1/areas/{area_id}/score          → Current score + signal
GET  /api/v1/areas/{area_id}/history        → Historical score timeline
GET  /api/v1/areas/{area_id}/breakdown      → 5-pillar breakdown + data layers
GET  /api/v1/areas/{area_id}/prediction     → 6/12/24 month forecast
GET  /api/v1/areas/compare?ids=a1,a2,a3     → Side-by-side comparison
GET  /api/v1/cities/{city_id}/heatmap       → All micro-area scores for map
GET  /api/v1/search?q=bandra+west           → Area search
GET  /api/v1/rankings?level=city&state=MH   → Ranked list with filters
POST /api/v1/watchlist                       → Add area to user watchlist
GET  /api/v1/alerts                          → User's triggered alerts
```

### 6.4 Database Layer

| Technology | Stores What | Why This Choice |
|---|---|---|
| **PostgreSQL** | Area profiles, user data, scores, signals, geographic hierarchy | Rock-solid relational DB, PostGIS for geo queries |
| **TimescaleDB** (PG extension) | Time-series score history, price history, trend data | Optimized for time-series — fast range queries on historical scores |
| **Redis** | Cache layer, session store, real-time leaderboards | Sub-millisecond reads for frequently accessed scores |
| **Elasticsearch** | Full-text area search, news article indexing | Fast fuzzy search ("Bandra" matches "Bandra West", "Bandra East") |
| **S3 / GCS Buckets** | Raw scraped data, PDFs, report snapshots | Cheap bulk storage for raw ingestion pipeline |

**Core Database Schema (Simplified):**
```
areas
├── area_id (UUID)
├── name ("Bandra West")
├── level (MICRO | CITY | STATE | NATIONAL)
├── parent_area_id (FK → areas)  // Mumbai for Bandra West
├── geometry (PostGIS POLYGON)
├── current_score (0-100)
├── current_signal (BUY | HOLD | REVIEW | AVOID)
└── last_scored_at (timestamp)

score_history  (TimescaleDB hypertable)
├── area_id (FK)
├── scored_at (timestamp)
├── total_score
├── p1_price_momentum
├── p2_rental_income
├── p3_liquidity
├── p4_infrastructure
└── p5_livability

data_points
├── area_id (FK)
├── category (CRIME | EDUCATION | HEALTH | ...)
├── metric_name ("crime_rate_per_1000")
├── value (numeric)
├── source ("NCRB 2025")
├── collected_at (timestamp)
└── agent_id (which agent collected this)
```

### 6.5 AI Agent Layer

| Technology | Purpose | Why This Choice |
|---|---|---|
| **LangChain / LangGraph** | Agent framework — tool use, chaining, memory | Most mature Python agent framework, great tool integration |
| **CrewAI** (alternative) | Multi-agent orchestration | Purpose-built for multi-agent collaboration with roles |
| **Gemini / GPT-4o API** | LLM backbone for agents | Reasoning, summarization, news analysis, sentiment extraction |
| **SerpAPI / Tavily** | Web search for Research Agent | Structured search results the agent can parse |
| **Scrapy + Playwright** | Web scraping for Data Agent | Scrapy for static sites, Playwright for JS-heavy portals (99acres, RERA) |
| **BeautifulSoup / Trafilatura** | HTML parsing & text extraction | Clean text from news articles and government pages |

**Agent ↔ System Integration:**
```
Orchestrator Agent
    │
    ├── triggers Research Agent  → uses SerpAPI/Tavily → saves findings to DB
    ├── triggers Data Agent      → uses Scrapy/APIs   → saves raw data to DB
    ├── triggers Prediction Agent → reads DB           → runs ML models → saves forecasts
    ├── triggers Signal Agent    → reads scores + predictions → publishes signals
    │
    └── all agents log actions to: agent_runs table (audit trail)
```

### 6.6 ML / Prediction Layer

| Technology | Purpose | Why This Choice |
|---|---|---|
| **Prophet (Meta)** | Time-series forecasting for price trends | Handles seasonality, trends, and holidays well — good for real estate cycles |
| **XGBoost / LightGBM** | Score prediction from tabular features | Best-in-class for structured data — all 10 data categories as features |
| **LSTM (PyTorch)** | Deep learning for complex temporal patterns | Captures long-term dependencies in multi-year price movements |
| **VADER + FinBERT** | News & social media sentiment analysis | VADER for quick sentiment, FinBERT for financial text nuance |
| **scikit-learn** | Feature engineering, normalization, evaluation | Standard toolkit — preprocessing, train/test split, metrics |
| **MLflow** | Model tracking & versioning | Track experiments, compare model performance, reproducibility |

**Prediction Pipeline:**
```
Raw Data (10 categories)
    → Feature Engineering (normalize, lag features, rolling averages)
        → Train Models (Prophet for trends, XGBoost for scoring)
            → Generate Forecasts (6mo, 12mo, 24mo horizons)
                → Confidence Intervals (how sure is the prediction)
                    → Feed to Signal Agent
```

### 6.7 Data Pipeline & Orchestration

| Technology | Purpose | Why This Choice |
|---|---|---|
| **Apache Airflow** | Pipeline orchestration & scheduling | Industry standard for data pipelines, DAG-based, great monitoring |
| **Scrapy** | Web scraping framework | Async spiders, rate limiting, retry logic, built for scale |
| **API Connectors (custom)** | Pull from NCRB, Census, CPCB, RERA APIs | Python scripts per data source |
| **Great Expectations** | Data quality validation | Catch bad data before it corrupts scores |
| **dbt** | Data transformation | SQL-based transforms for clean analytics tables |

**Scheduled DAGs (Airflow):**
```
Daily:
  ├── scrape_listing_prices      (99acres, MagicBricks, Housing.com)
  ├── fetch_aqi_data             (CPCB / SAFAR)
  ├── scan_news_sentiment        (Google News, real estate news sites)
  └── update_google_trends       (search interest per area)

Weekly:
  ├── scrape_rental_data         (NoBroker, MagicBricks rentals)
  ├── refresh_infrastructure     (metro/highway project tracker)
  ├── recalculate_all_scores     (full scoring cycle)
  └── generate_predictions       (run ML models)

Monthly:
  ├── pull_transaction_data      (IGR / registration data)
  ├── update_crime_stats         (NCRB when available)
  ├── refresh_demographics       (Census / survey data)
  └── generate_monthly_reports   (area performance summaries)
```

### 6.8 Infrastructure & Deployment

| Technology | Purpose | Why This Choice |
|---|---|---|
| **Docker + Docker Compose** | Containerization | Consistent environments, easy local dev + deployment |
| **Google Cloud Platform (GCP)** | Cloud hosting | Cloud Run for API, Cloud SQL for DB, GCS for storage |
| **GitHub Actions** | CI/CD pipeline | Auto-deploy on push, run tests, lint checks |
| **Prometheus + Grafana** | Monitoring & alerting | Track API latency, agent success rates, scraping health |
| **Sentry** | Error tracking | Catch and debug production errors fast |

### 6.9 End-to-End Data Flow (One Scoring Cycle)

```
STEP 1: COLLECT
    Airflow triggers daily DAGs
    → Scrapy spiders pull prices from 99acres, MagicBricks
    → API connectors pull AQI, crime, infra data
    → Research Agent searches web for news & announcements
    → Raw data lands in S3/GCS + data_points table

STEP 2: CLEAN & VALIDATE
    → Great Expectations validates incoming data
    → dbt transforms raw → staging → analytics tables
    → Outliers flagged, missing values handled

STEP 3: SCORE
    → Scoring Engine reads analytics tables
    → Normalizes each of 10 categories to 0–100
    → Applies 5-pillar formula with weights
    → Writes score to score_history (TimescaleDB)

STEP 4: PREDICT
    → Prediction Agent pulls score_history + features
    → Runs Prophet / XGBoost / LSTM models
    → Generates 6/12/24 month forecasts
    → Writes predictions to predictions table

STEP 5: SIGNAL
    → Signal Agent reads current score + prediction + momentum
    → Applies signal thresholds (BUY > 80, HOLD 60-79, etc.)
    → Adjusts for prediction confidence
    → Updates area.current_signal

STEP 6: SERVE
    → FastAPI serves fresh scores via REST endpoints
    → WebSocket pushes updates to connected dashboards
    → Redis caches hot data (top areas, city rankings)
    → User sees updated scores, charts, signals in real-time
```

---

## 7. Hierarchical Geographic Index — From Micro-Areas to States

The PlaceIndex score isn't just for one level — it works as a **hierarchical index** that scales from the smallest neighborhood up to the national level. The same formula applies everywhere, but the data granularity changes.

### 7.1 Geographic Levels

```
Level 1 (Micro)     →  Bandra West, Juhu, Worli, Lower Parel, Powai, Andheri East...
                          ↕ rolls up to
Level 2 (City)      →  Mumbai, Pune, Bangalore, Hyderabad, Delhi NCR...
                          ↕ rolls up to
Level 3 (State)     →  Maharashtra, Karnataka, Telangana, Delhi, Tamil Nadu...
                          ↕ rolls up to
Level 4 (National)  →  India (overall real estate index)
```

### 7.2 How It Works at Each Level

| Level | Example | What Gets Scored | Use Case |
|---|---|---|---|
| **Micro-Area** | Bandra West | Individual locality — most granular data | *"Should I buy a flat in Bandra West or Powai?"* |
| **City** | Mumbai | Weighted aggregate of all micro-areas in the city | *"Is Mumbai still a good city to invest in overall?"* |
| **State** | Maharashtra | Weighted aggregate of all cities in the state | *"Which state has the best real estate momentum?"* |
| **National** | India | Weighted aggregate of all states | *"How is India's real estate market doing vs. last year?"* |

### 7.3 Example — Mumbai Drill-Down

A user opens **Mumbai** on the dashboard and sees:

```
📍 MUMBAI — PlaceIndex Score: 72/100 — Signal: HOLD
├── 🟢 Bandra West    — Score: 85 — BUY      (strong infra + premium demand)
├── 🟢 Powai           — Score: 78 — BUY      (IT corridor growth + new metro)
├── 🟡 Juhu            — Score: 71 — HOLD     (stable but saturated)
├── 🟡 Lower Parel     — Score: 68 — HOLD     (commercial strong, residential flat)
├── 🟡 Worli           — Score: 65 — REVIEW   (luxury segment slowing)
├── 🔴 Mira Road       — Score: 42 — AVOID    (oversupply + poor infra delivery)
└── ...more areas
```

> The city-level score (72) is a **weighted average** of its micro-area scores, weighted by transaction volume and market size.

### 7.4 Roll-Up Logic

```
Micro-Area Score  = Direct calculation from 5 factors (raw data)
City Score        = Weighted average of micro-area scores (weight = transaction volume)
State Score       = Weighted average of city scores (weight = market size / GDP contribution)
National Score    = Weighted average of state scores (weight = state real estate market size)
```

### 7.5 The Scoring Formula (Applied at Every Level)

The same **5-factor formula** applies at every geographic level:

```
PlaceIndex Score = (w1 × CAGR_norm) + (w2 × Yield_norm) + (w3 × Liquidity_norm) 
                 + (w4 × Infra_norm) + (w5 × EcoDemo_norm)

Where:
  - Each factor is normalized to 0–100
  - Weights (w1–w5) sum to 1.0
  - Default weights: w1=0.25, w2=0.20, w3=0.20, w4=0.20, w5=0.15
  - Weights can be tuned per level (micro vs. city vs. state)
```

### 7.6 Signal Thresholds

| Score Range | Signal | Meaning |
|---|---|---|
| **80–100** | 🟢 **BUY** | Strong fundamentals + positive momentum — good time to invest |
| **60–79** | 🟡 **HOLD** | Stable area — hold existing investments, wait for clearer signals |
| **40–59** | 🟠 **REVIEW** | Mixed signals — do deeper research before committing |
| **0–39** | 🔴 **AVOID** | Weak fundamentals or negative trend — high risk |

### 7.7 What Makes This Powerful

- **Zoom in / zoom out** — Start at India level, drill into Maharashtra, then Mumbai, then Bandra West
- **Compare across levels** — Compare Bandra West vs. Koregaon Park (Pune) directly
- **Same formula everywhere** — Consistent, transparent scoring no matter the scale
- **AI agents feed every level** — Research and Data agents collect info at the micro level; it rolls up automatically

---

## 8. AI-Powered Planning Framework (7 Areas)

Before building the product, AI is used to **validate and de-risk** the idea across 7 dimensions:

| # | Planning Area | Purpose |
|---|---|---|
| 1 | **Market Demand Validation** | Confirm real user demand exists — search trends, forum analysis, survey design |
| 2 | **Data Strategy** | Identify, evaluate, and plan data acquisition (public, scraped, partnered) |
| 3 | **Scoring Model Testing** | Prototype the 5-factor model, test weighting, back-test against known outcomes |
| 4 | **Forecasting Approach** | Evaluate ML models for area-level price/score prediction |
| 5 | **UX / Persona Strategy** | Define target users (investor, NRI, first-time buyer) and tailor the experience |
| 6 | **Architecture Planning** | Plan the tech stack, data pipelines, and scalability approach |
| 7 | **Risk & Roadmap** | Identify risks (data gaps, regulatory, accuracy) and phase the build |

> [!IMPORTANT]
> The planning document frames all 7 areas as *"here's how AI helps you plan this responsibly"* — not *"here's the code."* The goal is validation before investment.

---

## 9. Target Users (Personas)

- **Real Estate Investors** — Looking for data-driven area picks, portfolio diversification
- **NRIs (Non-Resident Indians)** — Need remote visibility into which areas are worth investing in
- **First-Time Home Buyers** — Want to understand if an area is appreciating or stagnating
- **Real Estate Agents / Brokers** — Use as a credibility tool when advising clients
- **Developers / Builders** — Identify high-potential areas for new projects

---

## 10. Open Questions & Next Steps

- [ ] Finalize product name (PlaceIndex is a working title)
- [ ] Validate demand with real user research
- [ ] Identify initial city/cities for pilot
- [ ] Evaluate data source feasibility and costs
- [ ] Prototype the scoring model with sample data
- [ ] Define MVP scope vs. full vision
- [ ] Design agent communication protocol (how agents talk to each other)
- [ ] Decide agent update frequency (real-time vs. daily vs. weekly scoring cycles)
- [ ] Define geographic boundary data source (ward maps, pin code boundaries, etc.)
- [ ] Determine weighting strategy — fixed weights vs. user-adjustable vs. ML-optimized

---

## 11. Working Notes

*Use this section for freeform notes, edits, and ideas as the project evolves.*

---

> **This document is a living reference.** Edit freely as the concept develops.
