# PlaceIndex — Real-Time & Open Data Sources Directory

> **Master Directory of Data Sources** for the PlaceIndex platform — covering free APIs, open government data, geospatial queries, web scrapers, and commercial connectors across all 10 data categories.

---

## 🗺️ Quick Summary of Data Integration Methods

| Data Type | Primary Source | Access Method | Cost / Tier | Update Frequency |
|---|---|---|---|---|
| **Property Prices & Rentals** | 99acres, MagicBricks, Housing.com, NoBroker | Scrapy Spiders / Playwright | Scraped (Free) | Daily / Weekly |
| **Official Sales & Registrations** | IGR Maharashtra, CERSAI, MahaRERA | Govt Portals / Public Search | Open / Scraped | Monthly |
| **Geospatial & Amenities** | OpenStreetMap (Overpass API), Google Places API | REST API / Overpass QL | Free / Freemium | Real-time |
| **Transit & Travel Times** | Google Distance Matrix API, Transit APIs | REST API | Freemium | Real-time |
| **Air Quality (AQI)** | OpenAQ API, CPCB CAAQMS, WAQI API | REST API (JSON) | Free / Open | Hourly |
| **Crime Statistics** | NCRB (data.gov.in), Maharashtra Police Portal | Open Data (CSV/JSON) | Free | Annual / Quarterly |
| **Infrastructure News & Sentiment** | SerpAPI, GNews API, FinBERT NLP | REST API + Python ML | Freemium | Daily |
| **Demand Trends** | Google Trends (PyTrends API) | Python Library | Free | Daily |

---

## 📚 1. Category 1: Education & Schools

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **School Count & Coordinates** | OpenStreetMap (Overpass API) | `nwr["amenity"="school"](area.searchArea);` | Free, no API key required |
| **School Ratings & Reviews** | Google Places API (Nearby Search) | `https://maps.googleapis.com/maps/api/place/nearbysearch/json?type=school` | $200 free monthly credit |
| **Colleges & Universities** | OpenStreetMap / UGC Directory | `nwr["amenity"="university"](area.searchArea);` | Overpass QL query |
| **Coaching & Tuitions** | Google Places API / Local Directories | Text Search query `type=establishment` | Useful for student hub analysis |
| **Govt School Quality Baseline** | UDISE+ (data.gov.in) | Open Govt Data Portal CSV/API | Official board performance data |

---

## 🚔 2. Category 2: Crime & Safety

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Crime Rate per 1,000** | NCRB (National Crime Records Bureau) | `data.gov.in` Crime in India Datasets | District / Police station level |
| **Police Station Density** | OpenStreetMap (Overpass API) | `nwr["amenity"="police"](area.searchArea);` | Measure response proximity |
| **FIR / Incident Sentiment** | Local News Scraping + NLP | NewsAPI / GNews API | Scrapes localized safety news |
| **Gated Community Security** | Property Listing Features | Scrapy Parser (`gated_community=true`) | Percentage of secured societies |

---

## 🏥 3. Category 3: Healthcare & Hospitals

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Hospitals & Clinics Count** | OpenStreetMap (Overpass API) | `nwr["amenity"="hospital"](area.searchArea);` | Includes public & private |
| **Multi-Specialty Ratings** | Google Places API | Nearby Search `type=hospital` | Rating average & user reviews |
| **Pharmacies & Labs** | OpenStreetMap (Overpass API) | `nwr["amenity"="pharmacy"](area.searchArea);` | Day-to-day healthcare convenience |
| **Govt Hospital Beds** | NHP (National Health Portal / data.gov.in) | Open Govt API | Bed density per 1,000 citizens |

---

## 🏗️ 4. Category 4: Development & Construction Activity

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **RERA Registered Projects** | MahaRERA Portal (`maharera.mahaonline.gov.in`) | Web Scraper / Commercial RERA API | Track under-construction counts |
| **Developer Completion History** | MahaRERA Search & Filings | Scraped Project Certificates | Completion vs. delayed project ratio |
| **Building Permits & Cluster Schemes** | BMC / Municipal Corporation Portals | Municipal Notifications & Maps | Redevelopment / SRA project signals |

---

## 🚇 5. Category 5: Infrastructure & Connectivity

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Metro & Railway Stations** | OpenStreetMap (Overpass API) | `nwr["railway"="subway_entrance"](area);` | Direct distance to nearest station |
| **Travel Time to Commercial Hubs** | Google Distance Matrix API | `https://maps.googleapis.com/maps/api/distancematrix/json` | Driving/Transit time to BKC, Airport |
| **Upcoming Metro/Infra Progress** | MMRDA / DMRC Project Tracker Gazettes | Research Agent (SerpAPI + LLM) | Progress status (Planned, Active, Done) |
| **Bus Stop Density** | OpenStreetMap (Overpass API) | `nwr["highway"="bus_stop"](area);` | Feeder transport availability |
| **Road Network Quality** | OpenStreetMap Highway Tags | `way["highway"="primary"]` width & lanes | Infrastructure maturity proxy |

---

## 🏢 6. Category 6: Commercial & Economic Activity

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **IT Parks & Corporate Offices** | OpenStreetMap / LinkedIn Company Search | `nwr["office"="it"](area);` | White-collar job concentration |
| **Co-working Space Density** | Google Places API / Web Scraping | Search: "WeWork", "Awfis", "co-working" | Startup & freelancer ecosystem |
| **Restaurants, Cafes & Footfall** | Zomato API / Swiggy / OpenStreetMap | `nwr["amenity"="restaurant"](area);` | Lifestyle quotient & spending power |
| **Banks & ATM Density** | OpenStreetMap (Overpass API) | `nwr["amenity"="bank"](area);` | Financial services penetration |
| **Shopping Malls & Retail** | Google Places / OpenStreetMap | `nwr["shop"="mall"](area);` | Commercial retail ecosystem |

---

## 🌳 7. Category 7: Environment & Quality of Life

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Real-Time AQI (Air Quality)** | OpenAQ API (Free) | `https://api.openaq.org/v2/measurements?city=Mumbai` | Aggregates official CPCB sensors |
| **CPCB CAAQMS Direct Data** | CPCB Portal (`app.cpcbccr.com`) | Official CAAQMS Dashboard API | Real-time $PM_{2.5}, PM_{10}, NO_2$ |
| **WAQI Real-Time Feed** | World Air Quality Index API | `https://api.waqi.info/feed/mumbai/?token=YOUR_TOKEN` | Instant station AQI readings |
| **Green Cover / Satellite Vegetation** | Copernicus Sentinel-2 / Google Earth Engine | NDVI Index Calculation via PySTAC | Percentage of green parks & trees |
| **Flood & Waterlogging History** | IMD Rain Data / BMC Flood Prone Maps | Historical monsoon news + BMC GIS maps | Flood risk score deduction |

---

## 👥 8. Category 8: Demographics & Population

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Population Density** | Census of India / Ward Demographics | Data.gov.in / Census Portal | Density per sq. km |
| **Income & Purchasing Power Proxies** | NSSO Reports / RBI Housing Credit Data | RBI Bulletin Datasets | State & city level credit growth |
| **Migration & Population Growth** | Electoral Roll Aggregates (ECI) | State Election Commission Data | Voter growth rate per constituency |

---

## 💰 9. Category 9: Real Estate Market Data

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Asking Price per Sq. Ft.** | 99acres, MagicBricks, Housing.com | Custom Scrapy Spiders | Scrape resale & new launch listings |
| **Rental Rates & Yield %** | NoBroker, MagicBricks Rentals | Custom Scrapy Spiders | Calculate: $(\text{Annual Rent} / \text{Price}) \times 100$ |
| **Actual Sales Registration Prices** | IGR Maharashtra (Stamp Duty Dept) | Official Public Search Portal | Gold standard for actual sale price |
| **Transaction Volumes & Liquidity** | CERSAI / IGR Deed Registrations | Aggregated Monthly Deeds | Monthly property absorption rate |
| **Time-on-Market (Days)** | Listing Portal Tracking | Daily Scraping Delta | Measures how fast properties sell |

---

## 📡 10. Category 10: Emerging & Predictive Signals

| Data Point | Data Source | Access Method / API Endpoint | Notes |
|---|---|---|---|
| **Google Search Interest** | PyTrends (Google Trends API) | Python `pytrends.request.TrendReq` | Search interest for `"flats in Bandra"` |
| **News Sentiment Analysis** | GNews API / SerpAPI + FinBERT | REST API + HuggingFace FinBERT | Extract sentiment score $[-1, +1]$ |
| **Social Media Buzz & Complaints** | Twitter/X API / Reddit API (r/mumbai) | PRAW (Python Reddit API Wrapper) | Community feedback on civic issues |
| **State Budget Allocations** | State Govt Budget Documents | LLM Parsing of Budget Speeches | Forward-looking infra funding |

---

## 🛠️ Code Examples for Immediate Implementation

### 1. OpenStreetMap (Overpass API) Python Script
*Fetch all schools, hospitals, and transit stops in Bandra West for FREE without API keys:*

```python
import requests
import json

overpass_url = "http://overpass-api.de/api/interpreter"
overpass_query = """
[out:json][timeout:25];
area["name"="Mumbai"]->.searchArea;
(
  nwr["amenity"="school"](area.searchArea);
  nwr["amenity"="hospital"](area.searchArea);
  nwr["railway"="subway_entrance"](area.searchArea);
);
out center;
"""

response = requests.get(overpass_url, params={'data': overpass_query})
data = response.json()
print(f"Total amenities fetched: {len(data['elements'])}")
```

### 2. OpenAQ Free Real-Time Air Quality (AQI) Fetcher

```python
import requests

url = "https://api.openaq.org/v2/latest?city=Mumbai&limit=5"
response = requests.get(url)
results = response.json()['results']

for station in results:
    print(f"Station: {station['location']}")
    for measurement in station['measurements']:
        print(f"  - {measurement['parameter']}: {measurement['value']} {measurement['unit']}")
```

### 3. PyTrends Google Search Interest Fetcher

```python
from pytrends.request import TrendReq

pytrends = TrendReq(hl='en-US', tz=330)
kw_list = ["Flats in Bandra", "Flats in Powai", "Flats in Juhu"]
pytrends.build_payload(kw_list, cat=0, timeframe='today 12-m', geo='IN-MH')

data = pytrends.interest_over_time()
print(data.tail())
```

---

> **Next Step:** Integrate these connectors into the `Data Agent` and `Research Agent` pipeline!
