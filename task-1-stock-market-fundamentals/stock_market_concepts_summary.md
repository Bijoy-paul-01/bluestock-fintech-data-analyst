# Stock Market Fundamentals: Core Concepts & Principles

> **Domain Knowledge Reference Guide for FinTech Data Analysts**  
> *Targeted for Bluestock Fintech Onboarding & Financial Analytics*

---

## 1. What is a Stock Market?
A **Stock Market** (or equity market) is a regulated public marketplace where buyers and sellers trade equity shares of publicly listed corporations. It serves two foundational economic purposes:
1. **Primary Market (Capital Formation):** Enables corporations to raise capital directly from the public via Initial Public Offerings (IPOs) or Follow-on Public Offerings (FPOs).
2. **Secondary Market (Liquidity & Price Discovery):** Enables existing shareholders to buy and sell securities among themselves. Prices fluctuate in real time via an automated electronic limit order book (matching supply and demand).

---

## 2. Stock Exchanges: NSE & BSE
India’s equity trading ecosystem is anchored by two premier nationwide electronic exchanges regulated by SEBI:

| Parameter | National Stock Exchange (NSE) | Bombay Stock Exchange (BSE) |
| :--- | :--- | :--- |
| **Establishment** | 1992 (Commenced operations in 1994) | 1875 (Asia's oldest stock exchange) |
| **Benchmark Index** | **NIFTY 50** | **S&P BSE SENSEX** |
| **Market Share** | Dominates Equity Derivatives (F&O) & Cash segment (~90%+ F&O volume) | Historically dominant in Cash listings; rapid growth in derivatives |
| **Trading Technology** | NEAT (National Exchange for Automated Trading) | BOLT (BSE On-Line Trading System) |
| **Listed Companies** | ~2,300+ companies | ~5,400+ companies |

---

## 3. Benchmark Indices: Nifty 50 & Sensex
An **Index** is an aggregated statistical measure tracking the performance of a basket of representative stocks from various economic sectors.

* **NIFTY 50 (NSE):** Consists of 50 blue-chip companies across 13+ sectors of the Indian economy.
  * *Methodology:* **Free-Float Market Capitalization Weighted**.
  * *Base Year:* 1995 with a Base Value of **1,000**.
* **SENSEX (BSE - Sensitive Index):** Consists of 30 financially sound, highly liquid, industry-leading companies.
  * *Methodology:* **Free-Float Market Capitalization Weighted**.
  * *Base Year:* 1978–79 with a Base Value of **100**.

> **Free-Float Market Cap Methodology:** Only shares readily available for public trading (excluding promoter holdings, government stakes, and locked-in strategic shares) are factored into index weights:
> $$\text{Free-Float Market Cap} = \text{Share Price} \times (\text{Total Outstanding Shares} - \text{Locked/Promoter Shares})$$

---

## 4. Public Offerings: Mainboard IPO vs. SME IPO
An **Initial Public Offering (IPO)** is the transition process wherein a privately held company sells shares to institutional and retail investors to become publicly traded on a stock exchange.

| Feature | Mainboard IPO | SME IPO (NSE Emerge / BSE SME) |
| :--- | :--- | :--- |
| **Target Company Size** | Large, mature, profitable businesses | High-growth Small & Medium Enterprises |
| **Minimum Post-Issue Paid-up Capital** | ₹10 Crore minimum | ₹1 Crore min, maximum ₹25 Crore |
| **Track Record Requirement** | Min 3 years operating profit & net tangible assets | Min 2 to 3 years track record |
| **Minimum Application Lot Size** | ₹14,000 to ₹15,000 (~1 lot) | Minimum ₹1,00,000 to ₹2,00,000 per application |
| **Underwriting & Market Making** | Underwritten by Merchant Bankers; market making optional | 100% underwritten; mandatory Market Making for 3 years |
| **Retail Allotment Quota** | Minimum 35% (in general book-building) | Minimum 50% for retail/non-institutional investors |

---

## 5. Market Capitalization & SEBI Categorization
**Market Capitalization (Market Cap)** represents the aggregate market value of a listed company's outstanding equity shares:
$$\text{Market Capitalization} = \text{Current Market Price (CMP)} \times \text{Total Outstanding Shares}$$

### SEBI Categorization Framework (Mutual Fund Categorization Circular):
* **Large Cap:** Top **1st to 100th** company by full market capitalization (High stability, lower beta, blue-chip).
* **Mid Cap:** **101st to 250th** company by full market capitalization (Moderate risk, high growth potential).
* **Small Cap:** **251st company onwards** (Higher volatility, high growth upside, sensitive to liquidity).

---

## 6. Key Valuation Ratios & Metrics

### A. Price-to-Earnings Ratio (P/E Ratio)
$$\text{P/E Ratio} = \frac{\text{Current Market Price per Share}}{\text{Earnings Per Share (EPS)}}$$
* **Interpretation:** Measures how much investors are willing to pay per rupee of current earnings.
* **Trailing P/E:** Calculated using last 12 months (TTM) actual earnings.
* **Forward P/E:** Calculated using projected earnings for the next financial year.
* *FinTech context:* A high P/E indicates high future growth expectations or potential overvaluation.

### B. Price-to-Book Ratio (P/B Ratio)
$$\text{P/B Ratio} = \frac{\text{Current Market Price per Share}}{\text{Book Value per Share (BVPS)}} = \frac{\text{Market Capitalization}}{\text{Total Assets} - \text{Total Liabilities}}$$
* **Interpretation:** Compares market value to net accounting asset value (liquidation net worth).
* *FinTech context:* Vital for financial institutions, NBFCs, banks, and capital-intensive companies where tangible assets determine book value.

### C. Earnings Per Share (EPS)
$$\text{EPS} = \frac{\text{Net Profit after Tax (PAT)} - \text{Preference Dividends}}{\text{Weighted Average Number of Outstanding Shares}}$$
* **Basic EPS:** Calculated using currently issued common shares.
* **Diluted EPS:** Includes potential dilution from stock options (ESOPs), convertible debentures, and warrants.

### D. Dividend & Dividend Metrics
A **Dividend** is a direct cash distribution of corporate net profit to shareholders approved by the Board of Directors.
* **Dividend Yield (%):** $\frac{\text{Annual Dividend per Share}}{\text{Current Market Price}} \times 100$
* **Dividend Payout Ratio (%):** $\frac{\text{Total Dividends Paid}}{\text{Net Profit (PAT)}} \times 100$
* **Record Date vs. Ex-Dividend Date:** The **Record Date** is the cut-off date set by the company to verify eligible shareholders in depository records (NSDL/CDSL). The **Ex-Dividend Date** is the trading day on or after which the stock trades without dividend entitlement (under T+1 settlement, Ex-Date is typically the same as the Record Date).

### E. Bonus Shares vs. Stock Split

| Dimension | Bonus Issue | Stock Split |
| :--- | :--- | :--- |
| **Mechanism** | Issues additional free shares to existing shareholders by capitalizing free reserves/surplus. | Subdivides existing shares into smaller face-value units (e.g., FV ₹10 split to FV ₹2). |
| **Face Value** | **Remains Unchanged** (e.g., remains ₹10). | **Decreases Proportionately** (e.g., becomes ₹2). |
| **Reserves & Surplus** | Decreases (transferred to Equity Share Capital). | Unchanged. |
| **Market Price Impact** | Adjusts inversely to the bonus ratio (e.g., 1:1 split halves price). | Adjusts inversely to the split ratio (e.g., 1:5 split divides price by 5). |
| **Total Equity / Net Worth**| Remains identical; market cap remains identical. | Remains identical; market cap remains identical. |
| **Primary Objective** | Reward loyal shareholders; optimize balance sheet reserves. | Enhance retail liquidity and lower nominal per-share purchase price. |

### F. Trading Volume
**Volume** is the total number of shares transacted (bought and sold) during a given trading period.
* **Analytical Importance:** 
  1. **Trend Confirmation:** Price increases accompanied by rising volume confirm robust institutional accumulation; price increases on weak volume indicate exhaustion.
  2. **Liquidity & Impact Cost:** High-volume stocks offer tight bid-ask spreads, allowing large buy/sell orders without causing adverse price slippage.

---

## 7. Company Financial Statements: The Three Pillars

```
+-----------------------------------------------------------------------------------+
|                        1. Balance Sheet (Point in Time)                           |
|       Assets (What Company Owns)  =  Liabilities (Owed) + Equity (Net Worth)       |
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                     2. Profit & Loss Statement (Period of Time)                   |
|    Revenue - Operating Expenses = EBITDA - D&A = EBIT - Interest = EBT - Tax = PAT|
+-----------------------------------------+-----------------------------------------+
                                          |
                                          v
+-----------------------------------------------------------------------------------+
|                    3. Cash Flow Statement (Cash Reconciliations)                  |
|    Operating Cash Flow (CFO) + Investing Cash Flow (CFI) + Financing Cash (CFF)   |
+-----------------------------------------------------------------------------------+
```

### 1. Balance Sheet (Snapshot at Financial Year/Quarter End)
* **Assets:** Non-Current Assets (Property, Plant, Equipment, Intangible Tech/IP, Long-term Investments) + Current Assets (Cash, Marketable Securities, Inventories, Trade Receivables).
* **Liabilities:** Non-Current Liabilities (Long-term Borrowings, Lease obligations) + Current Liabilities (Trade Payables, Short-term Debt, Accrued Expenses).
* **Shareholders' Equity (Net Worth):** Equity Share Capital + Reserves & Surplus.

### 2. Profit & Loss Statement (P&L / Income Statement)
* **Revenue from Operations:** Core top-line business income.
* **Operating Expenses:** Raw materials, employee benefit costs, tech infrastructure, sales & admin expenses.
* **EBITDA:** Earnings Before Interest, Taxes, Depreciation, and Amortization (operational cash health).
* **EBIT (Operating Profit):** Operating efficiency after asset amortization.
* **Profit After Tax (PAT):** Bottom-line profit attributable to equity owners.

### 3. Cash Flow Statement (Cash Liquidity Analysis)
* **Cash Flow from Operating Activities (CFO):** Cash generated directly from primary operational activities (net profit adjusted for non-cash expenses and working capital changes).
* **Cash Flow from Investing Activities (CFI):** Capital expenditure (CapEx) in IT, infrastructure, or strategic financial investments.
* **Cash Flow from Financing Activities (CFF):** Inflows from equity/debt issuance minus outflows for debt servicing and dividend payouts.
* **Free Cash Flow (FCF):** $\text{FCF} = \text{CFO} - \text{Capital Expenditures (CapEx)}$.

---

## 8. Basic Financial Ratios Summary

| Ratio | Formula | Significance / Benchmark |
| :--- | :--- | :--- |
| **Return on Equity (ROE)** | $\frac{\text{PAT}}{\text{Shareholders' Equity}} \times 100$ | Capital efficiency for shareholders; $>15\%$ is considered healthy. |
| **Return on Capital Employed (ROCE)** | $\frac{\text{EBIT}}{\text{Total Assets} - \text{Current Liabilities}} \times 100$ | Overall capital generation regardless of debt vs equity financing; $>18-20\%$ preferred. |
| **Operating Profit Margin (OPM)** | $\frac{\text{Operating Profit (EBIT)}}{\text{Revenue from Operations}} \times 100$ | Pricing power and cost-control efficiency. |
| **Current Ratio** | $\frac{\text{Current Assets}}{\text{Current Liabilities}}$ | Short-term liquidity & solvency; $>1.5\text{x}$ indicates comfortable liquidity buffer. |
| **Debt-to-Equity (D/E)** | $\frac{\text{Total Debt}}{\text{Total Shareholders' Equity}}$ | Financial leverage; $<0.5\text{x}$ indicates conservative financial risk; $0$ is net-cash. |
