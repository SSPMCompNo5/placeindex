# Software Requirement Specification (SRS)
## PlaceIndex — Real Estate Area Investment Index & AI Swarm Platform

> **Document Standard:** IEEE Std 830-1998 / ISO/IEC/IEEE 29148  
> **Project Title:** PlaceIndex — Real Estate Area Investment Index Dashboard & Multi-Agent Intelligence Engine  
> **Document Version:** 1.0.0  
> **Date:** 2026-07-29  
> **Author:** SSPMCompNo5 (Final Year Computer Engineering Project Group)  
> **Status:** Approved / Release Candidate  

---

## Table of Contents
1. [Introduction](#1-introduction)
   - 1.1 Purpose
   - 1.2 Document Conventions
   - 1.3 Intended Audience
   - 1.4 Project Scope
   - 1.5 References
2. [Overall Description](#2-overall-description)
   - 2.1 Product Perspective
   - 2.2 Product Functions
   - 2.3 User Classes & Personas
   - 2.4 Operating Environment
   - 2.5 Constraints
   - 2.6 Assumptions & Dependencies
3. [Specific Functional Requirements](#3-specific-functional-requirements)
   - 3.1 Module 1: Data Acquisition & Pipeline Engine (FR-1)
   - 3.2 Module 2: 5-Pillar Scoring & Normalization Engine (FR-2)
   - 3.3 Module 3: Multi-AI Agent Swarm System (FR-3)
   - 3.4 Module 4: Predictive Forecasting & ML Engine (FR-4)
   - 3.5 Module 5: Spatial Hierarchical Roll-Up Engine (FR-5)
   - 3.6 Module 6: Interactive Dashboard & Visualization UI (FR-6)
   - 3.7 Module 7: User Management, Watchlists & Alerts (FR-7)
   - 3.8 Module 8: REST & WebSocket API Gateway (FR-8)
4. [External Interface Requirements](#4-external-interface-requirements)
   - 4.1 User Interfaces
   - 4.2 Hardware Interfaces
   - 4.3 Software Interfaces
   - 4.4 Communication Interfaces
5. [Non-Functional Requirements (NFRs)](#5-non-functional-requirements-nfrs)
   - 5.1 Performance Requirements
   - 5.2 Safety & Security Requirements
   - 5.3 Reliability & Availability
   - 5.4 Scalability & Maintainability
   - 5.5 Usability & Accessibility
6. [Data Requirements & Architectural Diagrams](#6-data-requirements--architectural-diagrams)
   - 6.1 Data Flow Diagrams (DFD Level 0 & Level 1)
   - 6.2 Entity-Relationship (ER) Schema

---

## 1. Introduction

### 1.1 Purpose
The purpose of this Software Requirement Specification (SRS) document is to provide a complete, formal description of the **PlaceIndex** platform. It details both functional and non-functional requirements, system architecture, external interfaces, data models, and constraints for developers, academic evaluators, and system architects.

### 1.2 Document Conventions
- **FR**: Functional Requirement
- **NFR**: Non-Functional Requirement
- **UI**: User Interface
- **API**: Application Programming Interface
- **CAGR**: Compound Annual Growth Rate
- **RERA**: Real Estate Regulatory Authority (MahaRERA)
- **AQI**: Air Quality Index
- **Priority**: High (Must Have), Medium (Should Have), Low (Nice to Have)

### 1.3 Intended Audience
This document is intended for:
1. **Academic Project Guides & Evaluators**: For assessing software engineering rigor, architecture, and scope.
2. **Software Engineers & Developers**: For implementing frontend, backend, ML models, and AI agent frameworks.
3. **Data Engineers**: For constructing Airflow pipelines, web scrapers, and database schemas.

### 1.4 Project Scope
**PlaceIndex** is a data-driven real estate intelligence platform that treats real estate **localities (neighborhoods / micro-markets)** like stocks traded on an exchange. Rather than evaluating single flats or buildings, PlaceIndex aggregates 40+ ground-level data points across 10 categories into a composite **PlaceIndex Score (0–100)** and outputs actionable investment stances (**Buy 🟢 / Hold 🟡 / Review 🟠 / Avoid 🔴**).

**In Scope:**
- Scraped and API-integrated data ingestion for Indian urban micro-markets (initial pilot: Mumbai).
- 5-Pillar composite scoring formula adhering to OECD guidelines.
- Autonomous multi-agent AI system (Research, Data, Prediction, Signal, Orchestrator).
- Hierarchical spatial aggregation (Micro-Area $\rightarrow$ City $\rightarrow$ State $\rightarrow$ National).
- Trading-app style web dashboard (charts, screeners, comparison tools, heat maps).

**Out of Scope (v1.0):**
- Direct property brokerage / e-commerce transaction handling.
- Legal title deed execution or escrow payments.

### 1.5 References
1. IEEE Std 830-1998: *IEEE Recommended Practice for Software Requirements Specifications*.
2. OECD (2008): *Handbook on Constructing Composite Indicators: Methodology and User Guide*.
3. PlaceIndex Master Reference (`PROJECT_REFERENCE.md`).
4. PlaceIndex Real-Time Data Directory (`REALTIME_DATA_SOURCES.md`).
5. PlaceIndex Academic Paper Framework (`RESEARCH_PAPERS.md`).

---

## 2. Overall Description

### 2.1 Product Perspective
PlaceIndex operates as an independent, cloud-native web platform. It interfaces with external data providers (OpenStreetMap, OpenAQ, CPCB, PyTrends, Government registries) via background scrapers and API connectors, processes data through an AI/ML intelligence layer, and serves responsive web experiences via a modern Next.js/FastAPI stack.

```
┌────────────────────────────────────────────────────────────────────────┐
│                        EXTERNAL DATA SOURCES                           │
│  Property Listings • OpenStreetMap • OpenAQ • MahaRERA • Google Trends │
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ Ingestion
┌───────────────────────────────────▼────────────────────────────────────┐
│                    PLACEINDEX BACKEND PLATFORM                         │
│  Airflow Pipeline • PostgreSQL/TimescaleDB • AI Agent Swarm • ML Engine│
└───────────────────────────────────┬────────────────────────────────────┘
                                    │ REST / WSS APIs
┌───────────────────────────────────▼────────────────────────────────────┐
│                    USER DASHBOARD INTERFACE                            │
│  Stock-Style Charts • Interactive Heat Map • Screener • Comparison UI  │
└────────────────────────────────────────────────────────────────────────┘
```

### 2.2 Product Functions
1. **Locality Profiling**: Generating standardized index cards and profiles for micro-markets (Bandra, Powai, Juhu, etc.).
2. **5-Pillar Score Calculation**: Computing weighted scores across Price Momentum, Rental Yield, Liquidity, Infrastructure, and Livability.
3. **AI Swarm Intelligence**: Autonomous agents executing live web research, scraping, trend prediction, and signal classification.
4. **Predictive Forecasting**: Predicting 6, 12, and 24-month score and price trends using hybrid ML models.
5. **Spatial Heat Maps**: Visualizing city-wide investment attractiveness overlaying geo-boundaries.
6. **Side-by-Side Area Screener**: Comparing 2 to 4 micro-markets across all 10 data categories.
7. **Automated User Alerts**: Pushing alerts when an area changes stance (e.g., HOLD $\rightarrow$ BUY).

### 2.3 User Classes & Personas

| User Class | Technical Expertise | Primary Goal | Frequency of Use |
|---|---|---|---|
| **Real Estate Investors** | Moderate | Identify undervalued micro-markets with high 2-3 year growth potential | Daily / Weekly |
| **NRIs (Non-Resident)** | High | Remote visibility into area trends without physical site visits | Weekly / Monthly |
| **First-Time Homebuyers** | Low to Moderate | Understand if an area has declining crime, good schools, and stable resale value | Occasional |
| **Brokers & Consultants** | High | Use data-driven score cards to advise clients credibly | Daily |
| **Academic Evaluators** | High | Evaluate methodology, multi-agent AI execution, and data accuracy | Exam / Project Review |

### 2.4 Operating Environment
- **Client Side**: Modern Web Browsers (Chrome 100+, Firefox 100+, Safari 15+, Edge) on Desktop, Tablet, and Mobile.
- **Backend Application Server**: Linux (Ubuntu 22.04 LTS / Docker Containers) running Python 3.10+ / FastAPI / Uvicorn.
- **Database Servers**: PostgreSQL 15+ with PostGIS 3.3 extension, TimescaleDB 2.10+, Redis 7.0+.
- **Data Pipeline Orchestrator**: Apache Airflow 2.6+.

### 2.5 Constraints
- **Scraping Limits**: Rate-limiting and robots.txt compliance when querying public listing portals.
- **API Budgets**: Restricting paid API usage (Google Maps Distance Matrix) through intelligent Redis caching.
- **Data Heterogeneity**: Combining weekly price data with annual census/crime reports requires temporal alignment algorithms.
- **Financial Advice Disclaimer**: The system must display non-advisory legal disclaimers ("For informational research purposes only").

### 2.6 Assumptions & Dependencies
- Open-access public APIs (OpenAQ, OpenStreetMap Overpass, PyTrends) remain operational and accessible.
- Geographic boundary files (GeoJSON/KML) for Mumbai ward and pin-code boundaries are available.
- Python ML libraries (scikit-learn, XGBoost, Prophet, PyTorch) remain supported.

---

## 3. Specific Functional Requirements

### 3.1 Module 1: Data Acquisition & Pipeline Engine (FR-1)

| Req ID | Description | Priority |
|---|---|---|
| **FR-1.1** | The system shall automatically scrape property resale prices, rental rates, and listing volumes from major real estate portals daily via Scrapy. | **High** |
| **FR-1.2** | The system shall query OpenStreetMap Overpass API to extract counts and spatial coordinates for schools, hospitals, transit entrances, and commercial offices per micro-area. | **High** |
| **FR-1.3** | The system shall fetch hourly real-time Air Quality Index (AQI) values ($PM_{2.5}, PM_{10}$) from OpenAQ and CPCB APIs. | **High** |
| **FR-1.4** | The system shall query Google Trends (PyTrends) daily to measure search interest volume for micro-market keywords. | **Medium** |
| **FR-1.5** | The system shall parse MahaRERA public project registration data to count active under-construction projects and developer completion ratios. | **Medium** |
| **FR-1.6** | The system shall run data validation checks using Great Expectations to flag missing values, negative prices, or extreme statistical outliers before database insertion. | **High** |

---

### 3.2 Module 2: 5-Pillar Scoring & Normalization Engine (FR-2)

| Req ID | Description | Priority |
|---|---|---|
| **FR-2.1** | The system shall normalize all raw indicators ($x_i$) across 10 categories to a standardized range $[0, 100]$ using Min-Max scaling with winsorized outlier caps (1st and 99th percentiles). | **High** |
| **FR-2.2** | The system shall handle inverted metrics (e.g., crime rates, distance to CBD, AQI, time-on-market) such that lower raw values map to higher normalized scores ($100 - \text{Score}$). | **High** |
| **FR-2.3** | The system shall calculate 5 sub-pillar scores: Price Momentum (P1: 25%), Rental Yield & Income (P2: 20%), Liquidity & Demand (P3: 20%), Infrastructure & Development (P4: 20%), and Livability & Growth Signals (P5: 15%). | **High** |
| **FR-2.4** | The system shall compute the final composite **PlaceIndex Score** using weighted sum aggregation:  $$\text{Score} = \sum_{k=1}^{5} w_k \cdot P_k$$ | **High** |
| **FR-2.5** | The system shall support dynamic weight re-calculation using Principal Component Analysis (PCA) on historical datasets. | **Medium** |

---

### 3.3 Module 3: Multi-AI Agent Swarm System (FR-3)

| Req ID | Description | Priority |
|---|---|---|
| **FR-3.1** | The system shall deploy a **Research Agent** with live search access (SerpAPI/GNews) to monitor infrastructure announcements, metro progress, and local news sentiment. | **High** |
| **FR-3.2** | The system shall deploy a **Data Agent** responsible for executing scraping tasks, API integrations, and schema validation. | **High** |
| **FR-3.3** | The system shall deploy a **Prediction Agent** that executes forecasting ML models based on cleaned tabular data and research signals. | **High** |
| **FR-3.4** | The system shall deploy a **Signal Agent** that converts scores and trend projections into investment stances (**Buy / Hold / Review / Avoid**). | **High** |
| **FR-3.5** | The system shall deploy an **Orchestrator Agent** to manage agent execution DAGs, log agent runs, and resolve conflicting outputs (e.g., high price growth vs. news of stalled infrastructure). | **High** |

---

### 3.4 Module 4: Predictive Forecasting & ML Engine (FR-4)

| Req ID | Description | Priority |
|---|---|---|
| **FR-4.1** | The system shall train a **Prophet** model on historical price time-series to extract baseline macro trends and annual seasonality cycles. | **High** |
| **FR-4.2** | The system shall train an **XGBoost Regressor** on non-price leading indicators (RERA projects, job density, AQI, news sentiment) to predict residual price momentum. | **High** |
| **FR-4.3** | The system shall output projected scores and price-per-sq-ft values for **6-month, 12-month, and 24-month** forward horizons with 95% confidence intervals. | **High** |
| **FR-4.4** | The system shall execute **FinBERT NLP** models on scraped real estate news to generate a 30-day moving sentiment index ($S_{\text{news}} \in [-1, +1]$) per micro-area. | **Medium** |

---

### 3.5 Module 5: Spatial Hierarchical Roll-Up Engine (FR-5)

| Req ID | Description | Priority |
|---|---|---|
| **FR-5.1** | The system shall maintain a 4-tier geographic spatial hierarchy (`MICRO` $\rightarrow$ `CITY` $\rightarrow$ `STATE` $\rightarrow$ `NATIONAL`). | **High** |
| **FR-5.2** | The system shall compute higher-level index scores (e.g. Mumbai City Score) using **Volume-Weighted Spatial Aggregation**:  $$\text{Score}_{\text{City}} = \frac{\sum (V_i \cdot S_i)}{\sum V_i}$$ where $V_i$ is monthly transaction volume of micro-area $i$. | **High** |
| **FR-5.3** | The system shall apply a **Spatial Spillover Model** where adjacent micro-area scores influence neighbor scores by up to 10% weight. | **Medium** |

---

### 3.6 Module 6: Interactive Dashboard & Visualization UI (FR-6)

| Req ID | Description | Priority |
|---|---|---|
| **FR-6.1** | The system shall render a **Stock Screener Interface** displaying ranked micro-markets with sorting, filtering (by price, yield, score, stance), and search. | **High** |
| **FR-6.2** | The system shall render **Interactive Stock-Style Trend Charts** (using D3.js) plotting historical score timelines against price movements. | **High** |
| **FR-6.3** | The system shall render an **Interactive Mapbox Heat Map** displaying city-wide micro-area scores overlaid on polygon boundaries. | **High** |
| **FR-6.4** | The system shall provide a **Side-by-Side Comparison Tool** allowing users to select 2 to 4 micro-areas and compare all 10 data categories simultaneously. | **High** |
| **FR-6.5** | The system shall provide a **Drill-Down Detail View** for every micro-area, showing pillar breakdown radar charts, leading indicators, and AI rationale summaries. | **High** |

---

### 3.7 Module 7: User Management, Watchlists & Alerts (FR-7)

| Req ID | Description | Priority |
|---|---|---|
| **FR-7.1** | The system shall support secure user registration and login using JWT (JSON Web Tokens) and OAuth 2.0. | **High** |
| **FR-7.2** | The system shall allow users to create and manage custom **Watchlists** of micro-markets. | **Medium** |
| **FR-7.3** | The system shall trigger automated email / web notifications when an area in a user's watchlist experiences a stance change (e.g., HOLD $\rightarrow$ BUY) or score shift $\ge 5$ points. | **Medium** |

---

### 3.8 Module 8: REST & WebSocket API Gateway (FR-8)

| Req ID | Description | Priority |
|---|---|---|
| **FR-8.1** | The system shall expose RESTful API endpoints for external consumption (`/api/v1/areas/{id}/score`, `/api/v1/search`, `/api/v1/compare`). | **High** |
| **FR-8.2** | The system shall expose WebSocket connections (`/ws/v1/live-scores`) for real-time score updates to connected client dashboards. | **Medium** |
| **FR-8.3** | The system shall enforce API rate-limiting (100 requests/minute per IP) using Redis token buckets. | **High** |

---

## 4. External Interface Requirements

### 4.1 User Interfaces
- **Theme**: Premium Dark Mode Financial Trading aesthetic (dark slate `#0B0F17`, emerald green `#10B981` for BUY, amber `#F59E0B` for HOLD, rose `#EF4444` for AVOID).
- **Responsiveness**: Mobile-first responsive grid adapting from 320px smartphones to 4K desktop monitors.
- **Charts**: High-performance D3.js SVG/Canvas rendering with smooth crosshair tooltips.

### 4.2 Hardware Interfaces
- No dedicated hardware interface required; operates on standard cloud infrastructure (x86_64 / ARM64 servers).

### 4.3 Software Interfaces
- **PostgreSQL 15+ & PostGIS**: Spatial polygon queries (`ST_Contains`, `ST_Distance`).
- **TimescaleDB**: Time-series hyper-tables for `score_history` storage.
- **Redis Cache**: Caching API responses with 300-second TTL.
- **Mapbox GL JS**: Vector tile map rendering.

### 4.4 Communication Interfaces
- **HTTP/2 & HTTPS**: Encrypted TLS 1.3 web traffic.
- **WebSocket (WSS)**: Bi-directional score streaming.
- **JSON**: Payload format for all API requests and responses.

---

## 5. Non-Functional Requirements (NFRs)

### 5.1 Performance Requirements
- **NFR-1 (API Latency)**: 95% of REST API requests shall respond in $< 200\text{ ms}$.
- **NFR-2 (Dashboard Initial Load)**: First Contentful Paint (FCP) shall occur within $< 1.2\text{ s}$ on standard 4G connections.
- **NFR-3 (Chart Frame Rate)**: D3.js chart zooming and panning shall maintain $\ge 60\text{ FPS}$.
- **NFR-4 (Scoring Throughput)**: The backend shall recalculate scores for 1,000 micro-markets in $< 15\text{ seconds}$.

### 5.2 Safety & Security Requirements
- **NFR-5 (Authentication)**: Passwords shall be hashed using `bcrypt` with a minimum cost factor of 12.
- **NFR-6 (Data Encryption)**: All data in transit shall use TLS 1.3; data at rest (S3/DB) shall be AES-256 encrypted.
- **NFR-7 (Injection Protection)**: All database queries shall use parameterized ORM queries (SQLAlchemy/Pydantic) to prevent SQL injection.
- **NFR-8 (CORS & Headers)**: Strict Cross-Origin Resource Sharing (CORS) policies and HTTP security headers (HSTS, CSP, X-Frame-Options) shall be enforced.

### 5.3 Reliability & Availability
- **NFR-9 (Uptime)**: The platform shall achieve $\ge 99.9\%$ system availability.
- **NFR-10 (Failover & Recovery)**: Automated database read-replica failover shall occur within $< 30\text{ seconds}$ in case of primary instance failure.

### 5.4 Scalability & Maintainability
- **NFR-11 (Horizontal Scaling)**: FastAPI application instances shall scale horizontally via GCP Cloud Run / Kubernetes based on CPU utilization ($>70\%$).
- **NFR-12 (Containerization)**: All system services (Frontend, Backend API, Airflow Worker, Redis) shall be fully containerized using Docker and Docker Compose.

### 5.5 Usability & Accessibility
- **NFR-13 (Accessibility)**: The UI shall comply with WCAG 2.1 Level AA guidelines (contrast ratio $\ge 4.5:1$, full keyboard navigation).
- **NFR-14 (Search Speed)**: Search autocompletion for micro-areas shall yield results in $< 50\text{ ms}$.

---

## 6. Data Requirements & Architectural Diagrams

### 6.1 Data Flow Diagrams (DFD)

#### DFD Level 0 (Context Diagram)

```
                       ┌─────────────────────────┐
                       │   External Data Sources │
                       │ (Portals, APIs, Maps)   │
                       └────────────┬────────────┘
                                    │ Raw Data Feeds
                                    ▼
┌──────────────┐             ┌──────────────┐             ┌──────────────┐
│  User /      │──Search/───►│  PLACEINDEX  │───Scores/──►│  User /      │
│  Investor    │  Query      │  SYSTEM      │   Signals   │  Investor    │
└──────────────┘             └──────────────┘             └──────────────┘
```

#### DFD Level 1 (System Subsystems)

```
[External Sources] ──► (1. Ingestion Engine) ──► [Raw S3 / Data Points DB]
                                                          │
                                                          ▼
                                              (2. 5-Pillar Scoring Engine)
                                                          │
                                                          ▼
[User Query] ───────► (4. FastAPI Gateway) ◄─── [Score History TimescaleDB]
                            ▲                             ▲
                            │                             │
                     (3. AI Agent Swarm & ML Engine) ─────┘
```

---

### 6.2 Entity-Relationship (ER) Schema

```
┌──────────────────────────────────┐        ┌──────────────────────────────────┐
│              AREAS               │        │          SCORE_HISTORY           │
├──────────────────────────────────┤        ├──────────────────────────────────┤
│ area_id (PK, UUID)               │1      *│ score_id (PK, UUID)              │
│ name (VARCHAR 100)               ├───────►│ area_id (FK, UUID)               │
│ level (ENUM: MICRO,CITY,STATE)   │        │ scored_at (TIMESTAMP)            │
│ parent_area_id (FK -> AREAS)     │        │ total_score (DECIMAL 4,1)        │
│ geometry (GEOMETRY: POLYGON)     │        │ p1_price_momentum (DECIMAL 4,1)  │
│ current_score (DECIMAL 4,1)      │        │ p2_rental_income (DECIMAL 4,1)   │
│ current_signal (ENUM)            │        │ p3_liquidity (DECIMAL 4,1)       │
│ updated_at (TIMESTAMP)           │        │ p4_infrastructure (DECIMAL 4,1)  │
└──────────────────────────────────┘        │ p5_livability (DECIMAL 4,1)      │
                                            └──────────────────────────────────┘
                                                             ▲
                                                             │ 1
                                                             │
┌──────────────────────────────────┐                         │ *
│           DATA_POINTS            │        ┌────────────────┴─────────────────┐
├──────────────────────────────────┤        │           PREDICTIONS            │
├──────────────────────────────────┤        ├──────────────────────────────────┤
│ point_id (PK, UUID)              │        │ prediction_id (PK, UUID)         │
│ area_id (FK, UUID)               │        │ area_id (FK, UUID)               │
│ category (ENUM: 1..10)           │        │ horizon_months (INTEGER: 6,12,24)│
│ metric_name (VARCHAR 100)        │        │ predicted_score (DECIMAL 4,1)    │
│ raw_value (NUMERIC)              │        │ confidence_lower (DECIMAL 4,1)   │
│ normalized_value (DECIMAL 4,1)   │        │ confidence_upper (DECIMAL 4,1)   │
│ source_name (VARCHAR 100)        │        │ model_version (VARCHAR 50)       │
│ collected_at (TIMESTAMP)         │        │ generated_at (TIMESTAMP)         │
└──────────────────────────────────┘        └──────────────────────────────────┘
```

---

> **Document Approval:**  
> **Prepared by:** SSPMCompNo5 Group  
> **Project Guide Signature:** ___________________________  
> **Department:** Computer Engineering  
> **Date:** July 29, 2026  
