# Bluestock FinTech — Data Analyst Prerequisite & Domain Assignments

![Bluestock FinTech Banner](https://img.shields.io/badge/Bluestock-FinTech%20Analytics-blue?style=for-the-badge&logo=appveyor)
![Python Version](https://img.shields.io/badge/Python-3.10%2B-green?style=for-the-badge&logo=python)
![Git & GitHub](https://img.shields.io/badge/Version%20Control-Git%20%26%20GitHub-orange?style=for-the-badge&logo=github)
![Architecture](https://img.shields.io/badge/Architecture-End--to--End%20Data%20Flow-purple?style=for-the-badge)

Welcome to the comprehensive assignment repository prepared for the **Bluestock FinTech Data Analyst** onboarding and domain prerequisites. This repository covers all five required modules with complete domain analyses, automated data pipelines, architecture schematics, and case studies.

---

## 📑 Repository Navigation & Module Index

| Module | Topic | Core Deliverables | Location |
| :---: | :--- | :--- | :--- |
| **01** | **Stock Market Fundamentals** | • 1-Page Domain Concepts Summary<br>• Audited 3-Year Financial Analysis of **BSE Limited** (P&L, Balance Sheet, Cash Flow, Ratios) | [`task-1-stock-market-fundamentals/`](./task-1-stock-market-fundamentals/) |
| **02** | **REST APIs & JSON** | • REST & JSON Engineering Reference Guide<br>• Automated Python API Extractor & Converter (`api_fetch_and_convert.py`)<br>• Exported Datasets (`market_data.json` & `market_data.csv`)<br>• Ready-to-import Postman / Bruno Collection | [`task-2-rest-apis-and-json/`](./task-2-rest-apis-and-json/) |
| **03** | **Git & GitHub** | • Git & GitHub End-to-End Workflow & PR Guide<br>• Git Command Cheatsheet<br>• Atomic Commit History & Remote Push Instructions | [`task-3-git-and-github/`](./task-3-git-and-github/) |
| **04** | **Software Development Concepts** | • Comprehensive FinTech Software Architecture Guide<br>• Mermaid Sequence & System Flowcharts<br>• Standalone Vector Architecture Diagram (`data_flow_diagram.svg`) | [`task-4-software-development-concepts/`](./task-4-software-development-concepts/) |
| **05** | **FinTech Business Understanding** | • Indian Capital Markets Ecosystem Guide (Demat, Depositories, SEBI, T+1)<br>• In-Depth Case Study: **How Zerodha Uses Data Analytics** (Nudge, Console, RMS, Behavioral ML) | [`task-5-fintech-business-understanding/`](./task-5-fintech-business-understanding/) |

---

## 📂 Project Directory Structure

```text
bluestock-fintech-data-analyst/
│
├── README.md                                          # Master repository documentation (this file)
├── .gitignore                                         # Python, environment, and OS ignore rules
│
├── task-1-stock-market-fundamentals/                  # MODULE 1: Stock Market Domain
│   ├── stock_market_concepts_summary.md               # 1-page executive summary of foundational concepts
│   └── company_financial_analysis_bse_ltd.md          # 3-year audited financial analysis of BSE Limited
│
├── task-2-rest-apis-and-json/                         # MODULE 2: APIs & Data Extraction
│   ├── README.md                                      # Guide on HTTP methods, status codes, JSON & auth
│   ├── api_fetch_and_convert.py                       # Python pipeline script (API -> JSON -> pandas -> CSV)
│   ├── data/
│   │   ├── market_data.json                           # Raw, formatted API JSON response payload
│   │   └── market_data.csv                            # Cleaned, enriched tabular dataset for analysis
│   └── postman/
│       └── bluestock_api_collection.json              # Postman / Bruno importable API collection
│
├── task-3-git-and-github/                             # MODULE 3: Version Control
│   ├── README.md                                      # Git & GitHub lifecycle, branches, and PR workflows
│   └── git_cheatsheet.md                              # Daily developer Git command cheatsheet
│
├── task-4-software-development-concepts/              # MODULE 4: Software Architecture
│   ├── README.md                                      # Frontend vs Backend, DBs (OLTP/OLAP), CDC, SDLC
│   └── diagrams/
│       ├── data_flow_architecture.md                  # Mermaid flowcharts & sequence diagrams
│       └── data_flow_diagram.svg                      # Standalone visual architecture diagram
│
└── task-5-fintech-business-understanding/             # MODULE 5: FinTech Business Understanding
    ├── README.md                                      # Demat, NSDL vs CDSL, SEBI, T+1 settlement cycle
    └── case_study_zerodha_data_analytics.md           # Zerodha case study on Nudge, Console & RMS analytics
```

---

## 🚀 Quickstart & Reproduction Guide

### 1. Prerequisites
Ensure you have Python 3.8+ installed on your system.

### 2. Install Required Python Dependencies
```bash
pip install requests pandas
```

### 3. Run the Automated Module 2 Data Pipeline
Execute the Python script to fetch real-time financial market data via REST API, validate the schema, save the JSON payload, and export the enriched tabular CSV:
```bash
python task-2-rest-apis-and-json/api_fetch_and_convert.py
```
*Outputs generated:*
* `task-2-rest-apis-and-json/data/market_data.json`
* `task-2-rest-apis-and-json/data/market_data.csv`

### 4. Test the API Collection in Postman or Bruno
1. Open **Postman** or **Bruno**.
2. Click **Import**.
3. Select `task-2-rest-apis-and-json/postman/bluestock_api_collection.json`.
4. Run the requests to view headers, query parameters, and execute automated test assertions.

### 5. Inspect the Architecture Diagram (Module 4)
Open [`task-4-software-development-concepts/diagrams/data_flow_diagram.svg`](./task-4-software-development-concepts/diagrams/data_flow_diagram.svg) directly in any modern browser (Chrome, Edge, Firefox) or image viewer to inspect the 7-tier data flow.

---

## 🛠️ Step-by-Step GitHub Upload Instructions (Module 3)

To upload this repository to your personal GitHub account:

```bash
# 1. Rename default branch to main (if not already main)
git branch -M main

# 2. Add your remote GitHub repository
git remote add origin https://github.com/<YOUR-USERNAME>/bluestock-fintech-data-analyst.git

# 3. Push all commits to your remote repository
git push -u origin main
```

---

## 📊 Summary of Module Solutions

### Module 1: Stock Market Fundamentals
* **Key Topics Covered:** Primary vs. Secondary markets, NSE & BSE history, Nifty 50 & Sensex weighting (free-float market cap), Mainboard IPO vs. SME IPO thresholds, SEBI Large/Mid/Small Cap classification, P/E, P/B, Basic vs. Diluted EPS, Dividends (Yield, Record/Ex-dates), Bonus vs. Stock Splits, Volume-Price correlation, Balance Sheet, P&L, Cash Flow (CFO, CFI, CFF), ROCE, ROE, Current Ratio, Debt-to-Equity, and Operating Margins.
* **Company Financial Statement Analysis:** Audited 3-year evaluation of **BSE Limited (NSE: BSE)** covering FY22–FY24. Highlights include BSE's 67.5% YoY revenue surge in FY24, 23.8% ROE, zero long-term debt, asset-light operating leverage, and derivatives market share growth.

### Module 2: REST APIs & JSON
* **Key Topics Covered:** API client-server model, HTTP methods (`GET`, `POST`, `PUT`, `PATCH`, `DELETE`), HTTP status codes (2xx, 4xx, 5xx), JSON data types, query vs. path parameters, Bearer JWT authentication, and Postman/Bruno workflows.
* **Implementation:** `api_fetch_and_convert.py` extracts live financial market records via HTTP GET, inspects response headers and JSON keys, computes volatility and liquidity metrics, and writes `market_data.json` and `market_data.csv`.

### Module 3: Git & GitHub
* **Key Topics Covered:** Distributed version control architecture, Working Directory $\rightarrow$ Staging $\rightarrow$ Local Repo $\rightarrow$ Remote Repo, branching strategies, resolving merge conflicts, Conventional Commits specification, and Pull Request (PR) review lifecycles.
* **Deliverables:** Step-by-step GitHub repository publishing guide, branching workflow documentation, and a daily command cheatsheet.

### Module 4: Basic Software Development Concepts
* **Key Topics Covered:** Frontend vs. Backend separation, Client-Server architecture, WebSockets for live tickers, OLTP (PostgreSQL) vs. OLAP (Snowflake/ClickHouse), In-Memory Caching (Redis), Change Data Capture (CDC via Debezium & Kafka), ELT transformations with dbt, structured JSON logging, circuit breakers, idempotency, and Agile SDLC.
* **Diagrams:** High-fidelity Mermaid sequence diagram and standalone SVG architecture diagram detailing data flow from **User Click $\rightarrow$ React App $\rightarrow$ API Gateway $\rightarrow$ FastAPI $\rightarrow$ PostgreSQL $\rightarrow$ Kafka CDC $\rightarrow$ Snowflake Warehouse $\rightarrow$ PowerBI Analytics Dashboard**.

### Module 5: FinTech Business Understanding
* **Key Topics Covered:** Discount vs. Full-service brokerages, 3-in-1 account triad (Bank, Trading, Demat), NSDL vs. CDSL depository operations, SEBI investor protection mandates, T+1 rolling settlement timeline, and market participants (Retail, HNIs, DIIs, FIIs/FPIs, QIBs, Prop desks, Market makers).
* **Case Study:** **Zerodha Broking Limited** — In-depth analysis of how data analytics powers **Zerodha Nudge** (real-time behavioral warnings reducing illiquid options losses by 40%+), **Console** (visual trade journaling, XIRR benchmarks, tax P&L), **RMS** (real-time VaR & predictive auto-square off), and business decisions (capacity planning, zero ad-spend organic growth).

---

## 👤 Author & Acknowledgments
* **Prepared for:** Bluestock FinTech Data Analyst Onboarding
* **Domain:** FinTech, Stock Markets, REST APIs & Financial Analytics
