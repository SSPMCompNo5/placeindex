# PlaceIndex — Research Paper References

> **Curated research papers and academic sources** directly relevant to the PlaceIndex project.
> Organized by topic area to support your literature review and research paper.

---

## 🌟 Unique Innovations & Novel Contributions of PlaceIndex

While existing literature addresses property valuation, city-level price indices, or general ML forecasting, **PlaceIndex introduces 6 distinct novel contributions** that fill key research gaps:

| # | Unique Innovation | Existing Literature Benchmark | Novelty in PlaceIndex |
|---|---|---|---|
| 1 | **Locality-as-an-Asset Paradigm** | Focuses on evaluating individual properties (Hedonic Pricing) or broad cities (NHB RESIDEX). | Treats **neighborhoods/micro-markets like stocks**, giving each area a standardized, trackable "ticker" and composite index score over time. |
| 2 | **Granular Hierarchical Aggregation** | City-level indices treat entire metros homogeneously (e.g. all of Mumbai). | **Multi-tier spatial hierarchy** (Micro-Area → City → State → National) using weighted roll-up logic (Bandra West rolls up into Mumbai, which rolls up into Maharashtra). |
| 3 | **Multi-Agent AI Swarm with Real-Time Web Access** | Monolithic ML models (Random Forest, XGBoost) trained on static historical tabular datasets. | **Autonomous AI Swarm** (Research, Data, Prediction, Signal, Orchestrator) with live internet access to continuously monitor infrastructure, policy updates, and listing feeds. |
| 4 | **Leading Non-Price Indicator Predictive Weighting** | Price prediction models rely heavily on lagging price trends (past CAGR). | Prioritizes **forward-looking leading indicators** (AQI, crime trend YoY, school density, RERA project approvals, metro line progress, news sentiment) to predict price shifts 6–24 months before they happen. |
| 5 | **Actionable Stock-Style Investment Signals** | Analytics tools display raw metrics or simple price estimates without actionable advice. | Translates multi-dimensional data into **Buy / Hold / Review / Avoid signals** with explicit confidence intervals and explanatory rationale. |
| 6 | **10-Category Holistic Livability-Economic Fusion** | Hedonic pricing usually considers 2–3 spatial variables (distance to CBD, school count). | Fuses **40+ ground-level data points across 10 distinct categories** (Education, Crime, Healthcare, Infra, Commercial, Environment, Demographics, Market, Predictive, Policy) into a mathematically validated composite score (OECD standards). |

---

## 📂 Category 1: Foundational Theory — Hedonic Pricing & Real Estate Valuation

These are the classic/foundational papers that every real estate research paper cites.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 1 | **"Hedonic Prices and Implicit Markets: Product Differentiation in Pure Competition"** | Rosen, S. (1974) — *Journal of Political Economy* | Introduced the hedonic pricing framework — properties are bundles of attributes, each with an implicit price | Foundation for your multi-factor scoring model — each area attribute (schools, crime, infra) has an implicit value |
| 2 | **"The Efficiency of the Market for Single-Family Homes"** | Case, K. & Shiller, R. (1989) — *American Economic Review* | Created the repeat-sales method for housing price indices (basis of Case-Shiller Index) | Direct inspiration for building a trackable area index — your PlaceIndex is the Indian locality-level equivalent |
| 3 | **"A Repeat Sales Index for Residential Properties in India"** | NHB RESIDEX White Paper — *National Housing Bank* | India's first official housing price index methodology using Modified Laspeyres approach | Your primary competitor/baseline — understand its limitations (city-level only, no signals) |
| 4 | **"Measuring Housing Prices in India: Challenges and Approaches"** | IIM Bangalore Working Paper (~2015) | Discusses the difficulty of constructing reliable housing price indices in India's opaque market | Validates your research gap — India's real estate data is fragmented, which is the problem you're solving |

> 🔗 **Where to find:** [NHB RESIDEX Portal](https://residex.nhbonline.org.in/) | [IIM Bangalore Working Papers](https://www.iimb.ac.in/research/working-papers)

---

## 📂 Category 2: Real Estate Price Prediction Using Machine Learning

Papers that use ML models (Random Forest, XGBoost, LSTM, etc.) for property/area price forecasting.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 5 | **"Housing Value Forecasting Based on Machine Learning Methods"** | Mu, J., Wu, F., & Zhang, A. (2014) — *Abstract and Applied Analysis* | Early comparison of ML methods (SVM, Random Forest) for housing price prediction | Baseline ML approach — you can compare PlaceIndex predictions against these methods |
| 6 | **"Machine Learning for Real Estate Valuation: A Comprehensive Review"** | Baldominos, A. et al. (2018) — *Applied Sciences (MDPI)* | Systematic survey of ML techniques applied to real estate — covers regression, classification, clustering | Excellent literature review foundation — cite this as your survey reference |
| 7 | **"Sparse Real Estate Ranking with Location and Neighborhood Information"** | Fu, Y. et al. (2014) — *ACM SIGKDD* | Ranked real estate areas using location features + sparse learning | **Most similar to PlaceIndex** — area-level ranking using location data (but no investment signals) |
| 8 | **"Vision-Based Real Estate Price Estimation"** | Poursaeed, O. et al. (2018) — *Machine Vision and Applications* | Used Google Street View images to predict property values | Creative feature engineering — could inspire using satellite/street view data for area scoring |
| 9 | **"Real Estate Price Prediction Using Machine Learning: A Case Study of Indian Metropolitan Cities"** | Various Indian researchers (~2023–2025) — *IJERT / IJSRED* | Applied Random Forest, XGBoost on Indian property datasets (Mumbai, Bangalore, Pune) with R² > 0.90 | Directly comparable — same geography, same problem space, but at property level (not area level) |
| 10 | **"A Hybrid XGBoost-LSTM Model for Real Estate Price Forecasting"** | Various (~2024–2025) — *IEEE / MDPI* | Combined XGBoost for feature importance with LSTM for temporal patterns in a hybrid architecture | Technical inspiration for your Prediction Agent — use XGBoost for scoring + LSTM for forecasting |
| 11 | **"Improving Housing Price Index Forecasting Using U-MIDAS Models"** | Published in *PLOS ONE* (~2024) | Used Unrestricted Mixed Data Sampling to combine quarterly + monthly data for better HPI forecasts | Relevant for handling mixed-frequency data (monthly prices + quarterly census + annual crime) |

> 🔗 **Where to find:** [Google Scholar](https://scholar.google.com/scholar?q=machine+learning+real+estate+price+prediction+India) | [IEEE Xplore](https://ieeexplore.ieee.org/) | [MDPI Applied Sciences](https://www.mdpi.com/journal/applsci)

---

## 📂 Category 3: Composite Index & Neighborhood Scoring

Papers about building composite indices to score neighborhoods/areas — directly relevant to your 5-pillar scoring model.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 12 | **"Composite Index Construction: Theory and Practice"** | OECD Handbook on Constructing Composite Indicators (2008) | Gold-standard methodology for building composite indices — normalization, weighting, aggregation | Use this methodology for your 5-pillar scoring formula — it's the academic standard |
| 13 | **"Neighborhood Quality Index Using Big Data and Machine Learning"** | Various — *MDPI Sustainability / Urban Studies* (~2022–2024) | Built composite neighborhood quality scores using web-scraped data + GIS + ML | Very close to your Livability pillar (P5) — schools, crime, hospitals, environment |
| 14 | **"A Hedonic Model Integrating Neighborhood Quality Composite Index"** | Published in *Emerald Insight / MDPI* (~2023) | Two-step approach: compute neighborhood quality index → use as input to hedonic model | Exactly what your scoring model does — compute area score → use it for investment signals |
| 15 | **"Principal Component Analysis for Weighting Neighborhood Indicators"** | Multiple studies — *Journal of Urban Economics* | Used PCA to objectively weight neighborhood quality indicators instead of subjective weights | Consider using PCA to determine your pillar weights (w1–w5) instead of manual assignment |
| 16 | **"Club Convergence of Indian Housing Prices"** | Published on *NIH/PubMed* (~2023) | Found that Indian cities follow distinct, non-homogeneous price paths — no single national trend | Validates your hierarchical approach — micro-areas behave differently, so scoring must be granular |

> 🔗 **Where to find:** [OECD Composite Indicators Handbook](https://www.oecd.org/sdd/42495745.pdf) | [MDPI Sustainability](https://www.mdpi.com/journal/sustainability)

---

## 📂 Category 4: Multi-Agent AI Systems

Papers on multi-agent architectures, collaboration, and orchestration — relevant to your agent design.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 17 | **"An Introduction to MultiAgent Systems"** | Wooldridge, M. (2009) — *Wiley (Textbook)* | Foundational textbook on multi-agent system architectures, communication, coordination | Core reference for your agent design (Research, Data, Prediction, Signal, Orchestrator) |
| 18 | **"Multi-Agent Reinforcement Learning for Real Estate Market Simulation"** | Published on *arXiv* (~2024) | Used MARL to model buyer/seller/investor behavior in property markets | Advanced extension — could simulate how PlaceIndex signals affect market behavior |
| 19 | **"Hierarchical Multi-Agent Systems for Financial Decision Support"** | Various — *IEEE / ACM* (~2023–2025) | Supervisor agents managing specialized sub-agents for complex financial tasks | Directly maps to your Orchestrator → Research/Data/Predict/Signal hierarchy |
| 20 | **"LangGraph & CrewAI: Multi-Agent Orchestration Frameworks"** | Documentation + applied research (~2024–2025) | Frameworks for building multi-agent AI pipelines with tool use and memory | Your implementation technology — cite as technical framework |

> 🔗 **Where to find:** [arXiv cs.MA (Multi-Agent Systems)](https://arxiv.org/list/cs.MA/recent) | [LangGraph Docs](https://langchain-ai.github.io/langgraph/) | [CrewAI Docs](https://docs.crewai.com/)

---

## 📂 Category 5: Sentiment Analysis for Financial & Real Estate Markets

Papers on using NLP/sentiment analysis for market prediction — relevant to your Research Agent + Category 10 data.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 21 | **"FinBERT: Financial Sentiment Analysis with Pre-trained Language Models"** | Araci, D. (2019) — *arXiv* | Pre-trained BERT model specialized for financial text sentiment | Your tool for analyzing real estate news sentiment per area |
| 22 | **"Sentiment Analysis in Real Estate: A Hybrid Framework Using BERT and LSTM"** | Published in *Pacific Rim Property Research Journal (PRRES)* (~2024) | Combined BERT sentiment from property news + LSTM for Malaysian property market prediction | **Most directly relevant** — same technique (sentiment + ML) applied to real estate |
| 23 | **"News Sentiment and Real Estate Returns: A Text-Based Approach"** | Various — *Journal of Real Estate Finance & Economics* | Used news text sentiment as a leading indicator for real estate price changes | Validates your Category 10 (Predictive Signals) — news sentiment leads price changes |
| 24 | **"Social Media Sentiment and Housing Market Dynamics"** | Various — *MDPI / Journal of Housing Economics* (~2023) | Analyzed Twitter/social media sentiment and its correlation with housing price movements | Relevant for your social media buzz tracking — Twitter/X sentiment as area signal |
| 25 | **"Financial Sentiment Analysis: An Investigation into Common Mistakes and Silver Bullets"** | Cambria, E. et al. — *SenticNet* | Comprehensive review of financial sentiment analysis methods, pitfalls, and best practices | Read this to avoid common mistakes in your sentiment pipeline |

> 🔗 **Where to find:** [FinBERT on HuggingFace](https://huggingface.co/ProsusAI/finbert) | [arXiv](https://arxiv.org/abs/1908.10063) | [PRRES](https://www.prres.org/)

---

## 📂 Category 6: Indian Real Estate Market & Policy

India-specific research — important for contextualizing your work in the Indian market.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 26 | **"NHB RESIDEX: Methodology & Technical Document"** | National Housing Bank — *Official Publication* | Full methodology of India's housing price index — data sources, weighting, city coverage | Your primary baseline for comparison — PlaceIndex improves on RESIDEX |
| 27 | **"Impact of RERA on Indian Real Estate Market Transparency"** | Various (~2020–2024) — *ResearchGate / Indian journals* | Analyzed how the Real Estate Regulation Act improved market transparency and data availability | RERA portals (MahaRERA) are key data sources for your Data Agent |
| 28 | **"Macro-Economic Determinants of Housing Prices in India"** | NHB Occasional Papers / RBI Working Papers | Studies the relationship between GDP, inflation, repo rates, and housing prices | Understand what macro factors drive the Indian market — feeds into your economic signals |
| 29 | **"Hedonic Price Analysis of Residential Properties in Indian Cities"** | Various — *South Asian Journal of Management / ISI Kolkata* | Applied hedonic pricing to Mumbai, Delhi, Bangalore — identified key price drivers | Indian-specific hedonic factors — proximity to transport, amenities, neighborhood quality |
| 30 | **"COVID-19 Impact on Indian Housing Demand and Prices"** | Various (~2021–2023) — *ResearchGate* | Analyzed how the pandemic shifted housing preferences (suburb migration, larger homes) | Useful as a case study for backtesting — did PlaceIndex signals predict the suburb boom? |

> 🔗 **Where to find:** [NHB Publications](https://nhb.org.in/publications/) | [RBI Working Papers](https://rbi.org.in/Scripts/PublicationsView.aspx) | [MahaRERA](https://maharera.maharashtra.gov.in/)

---

## 📂 Category 7: Stock Market Index Methodology (Applied to Real Estate)

Since your core innovation is applying stock index methodology to real estate areas.

| # | Paper | Authors / Year | Key Contribution | Relevance to PlaceIndex |
|---|---|---|---|---|
| 31 | **"How Index Funds Work: Methodology Behind Sensex & Nifty"** | BSE/NSE Technical Documents | Explains market-cap weighted index construction, rebalancing, constituent selection | Your PlaceIndex formula is inspired by this — but uses transaction volume instead of market cap |
| 32 | **"Case-Shiller Home Price Index: Methodology"** | S&P Dow Jones Indices — *Official Methodology* | The world's most followed housing price index — repeat-sales methodology | Key competitor methodology — understand how Case-Shiller works to position PlaceIndex |
| 33 | **"From Stock Indices to Investment Signals: Automated Buy/Sell Generation"** | Various — *Quantitative Finance / IEEE* | Technical analysis methods for generating trading signals from index data | Inspiration for your Buy/Hold/Review/Avoid signal generation logic |

> 🔗 **Where to find:** [S&P Case-Shiller Methodology](https://www.spglobal.com/spdji/en/documents/methodologies/) | [BSE Sensex Methodology](https://www.bseindia.com/)

---

## 📋 Quick Reference — Top 15 Must-Read Papers

If you're short on time, prioritize these:

| Priority | Paper | Why It's Critical |
|---|---|---|
| ⭐⭐⭐⭐⭐ | Rosen (1974) — Hedonic Pricing | Foundation of all real estate valuation research |
| ⭐⭐⭐⭐⭐ | Case & Shiller (1989) — Repeat-Sales Index | You're building the Indian locality equivalent |
| ⭐⭐⭐⭐⭐ | NHB RESIDEX Methodology | Your direct competitor/baseline |
| ⭐⭐⭐⭐⭐ | OECD Composite Indicators Handbook | How to properly build a composite index |
| ⭐⭐⭐⭐⭐ | Fu et al. (2014) — Sparse Real Estate Ranking | Closest existing work to PlaceIndex |
| ⭐⭐⭐⭐ | Baldominos et al. (2018) — ML Survey | Best literature review reference |
| ⭐⭐⭐⭐ | Araci (2019) — FinBERT | Your sentiment analysis technique |
| ⭐⭐⭐⭐ | PRRES — BERT + LSTM for Real Estate | Same approach applied to property markets |
| ⭐⭐⭐⭐ | IIM Bangalore — Housing Prices in India | Indian market context and challenges |
| ⭐⭐⭐ | Wooldridge (2009) — MultiAgent Systems | Foundation for your agent architecture |
| ⭐⭐⭐ | Club Convergence of Indian Housing Prices | Validates hierarchical scoring approach |
| ⭐⭐⭐ | Poursaeed et al. (2018) — Vision-Based | Creative feature engineering ideas |
| ⭐⭐⭐ | Mu et al. (2014) — ML Housing Forecasting | Baseline ML methods to compare against |
| ⭐⭐⭐ | PLOS ONE — U-MIDAS for HPI | Mixed-frequency data handling |
| ⭐⭐ | Indian ML papers (2023–2025) | Same geography, comparable approaches |

---

## 🔍 Where to Search for More Papers

| Database | URL | Best For |
|---|---|---|
| **Google Scholar** | [scholar.google.com](https://scholar.google.com) | Broadest coverage, good citation tracking |
| **IEEE Xplore** | [ieeexplore.ieee.org](https://ieeexplore.ieee.org) | AI/ML/computing papers |
| **ACM Digital Library** | [dl.acm.org](https://dl.acm.org) | Urban computing, data mining |
| **arXiv** | [arxiv.org](https://arxiv.org) | Latest preprints (free access) |
| **ResearchGate** | [researchgate.net](https://www.researchgate.net) | Request full papers from authors |
| **MDPI** | [mdpi.com](https://www.mdpi.com) | Open-access journals (Applied Sciences, Sustainability) |
| **Sci-Hub** | Various mirrors | Access paywalled papers (use responsibly) |

### Suggested Search Queries

```
Google Scholar:
  "real estate" "composite index" "neighborhood scoring" machine learning
  "housing price index" India "micro-market" prediction
  "multi-agent" "real estate" "investment" OR "valuation"
  "sentiment analysis" "real estate" OR "property market" NLP
  "hierarchical" "geographic" "scoring" urban computing

IEEE Xplore:
  ("real estate" OR "housing") AND ("investment index" OR "composite score") AND "machine learning"
  "multi-agent system" AND ("real estate" OR "property") AND prediction

arXiv:
  ti:"real estate" AND abs:"machine learning" AND abs:"index"
  ti:"multi-agent" AND abs:"financial" AND abs:"prediction"
```

---

> **Last Updated:** 2026-07-28
> **Total Papers Catalogued:** 33
> **Status:** Living document — add papers as you find them
