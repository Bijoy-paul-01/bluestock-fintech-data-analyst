# Indian FinTech & Capital Markets Ecosystem: Business Understanding

> **Module 5 Reference Guide**  
> *Targeted for Bluestock Fintech Onboarding & Financial Analytics*

---

## 1. Brokerage Platforms: Full-Service vs. Discount Brokers

The Indian retail brokerage landscape underwent a massive disruption over the last decade, transitioning from legacy percentage-based offline models to digital-first, low-cost discount models:

| Feature | Discount Brokers (e.g., Zerodha, Groww, Angel One) | Full-Service Brokers (e.g., ICICI Direct, HDFC Securities, Motilal Oswal) |
| :--- | :--- | :--- |
| **Brokerage Pricing** | Flat fee (e.g., ₹20 or 0.03% per executed trade); ₹0 on equity delivery | Percentage of transaction turnover (e.g., 0.15% to 0.50% per trade) |
| **Research & Advisory** | Do **not** provide stock tips or proprietary research reports (pure execution) | In-house equity research reports, relationship managers, and advisory calls |
| **Platform Infrastructure** | Proprietary, high-concurrency web and mobile apps (Kite, Groww App) | Branch networks, tele-calling desks, and traditional desktop trading terminals |
| **Account Opening** | 100% digital paperless onboarding via Aadhaar e-Sign & DigiLocker (< 5 mins) | Historically physical paperwork, now hybrid digital |
| **Revenue Model** | High volume of F&O trades, float interest on unallocated funds, MTF (Margin Trading Facility), API subscriptions | High per-trade brokerage fees, portfolio management services (PMS), loan against shares |

---

## 2. Demat vs. Trading vs. Bank Accounts: The 3-in-1 Architecture

Understanding how retail investors participate in financial markets requires distinguishing the three distinct accounts:

```
+----------------------------------------------------------------------------------------------------+
|                                    THE TRADING ECOSYSTEM TRIAD                                     |
+------------------------------------+--------------------------------+------------------------------+
|          1. BANK ACCOUNT           |       2. TRADING ACCOUNT       |       3. DEMAT ACCOUNT       |
+------------------------------------+--------------------------------+------------------------------+
| • Holds Liquidity (Cash / INR)     | • Interface with Stock Exchange| • Holds Securities Digitally |
| • Regulated by RBI                 | • Managed by Registered Broker | • Managed by Depositories    |
| • Sources funds for buying shares  | • Places Buy/Sell Orders       | • Dematerialized shares/ETFs |
+------------------------------------+--------------------------------+------------------------------+
```

* **Demat Account (Dematerialized Account):** An electronic vault that holds shares, debentures, government bonds, and mutual fund units in digital format, eliminating paper certificate fraud, bad deliveries, and physical theft.
* **Beneficiary Owner ID (BOID):** A unique 16-digit alphanumeric identification number assigned to every investor's Demat account.

---

## 3. Depositories: NSDL & CDSL

Depositories are the central electronic custody banks for securities in India. Retail investors cannot open accounts directly with depositories; they interact through **Depository Participants (DPs)**, such as brokerages (Zerodha, Angel One) or commercial banks.

| Dimension | NSDL (National Securities Depository Limited) | CDSL (Central Depository Services Limited) |
| :--- | :--- | :--- |
| **Establishment** | 1996 (First depository in India) | 1999 |
| **Primary Promoters** | NSE, IDBI Bank, UTI | BSE, State Bank of India, Bank of India |
| **Target Strength** | Historically dominant in institutional & corporate custody | Dominant in retail retail Demat accounts (~70%+ retail market share) |
| **BO ID Structure** | 16 characters: starts with letters `"IN"` followed by 14 digits | 16 numeric digits |
| **Listing Status** | Preparing for IPO | Publicly listed on NSE (`NSE: CDSL`) |

---

## 4. Market Regulator: SEBI (Securities and Exchange Board of India)

Established under the **SEBI Act, 1992**, SEBI is the statutory market watchdog responsible for:
1. **Protecting Investor Interests:** Mandating strict risk disclosures (e.g., *“9 out of 10 individual traders in equity F&O incurred net losses”*), enforcing KYC verification, and regulating advertising claims.
2. **Promoting Market Development:** Pioneering world-class financial infrastructure (T+1 rolling settlement, ASBA for IPOs, interoperability of clearing corporations).
3. **Regulating Market Intermediaries:** Licensing and auditing stock exchanges, clearing corporations, depositories, brokers, and mutual funds.
4. **Preventing Market Manipulation:** Operating automated surveillance systems to detect insider trading, circular wash sales, front-running, and price rigging.

---

## 5. The Trading & Settlement Lifecycle (T+1 Rolling Settlement)

India is among the first major financial markets in the world to successfully transition to **T+1 rolling settlement** for all equities:

```
+----------------------------------------------------------------------------------------------------+
|                               THE T+1 TRADING & SETTLEMENT CYCLE                                   |
+----------------------------------------------------------------------------------------------------+

  DAY T (Trading Day - e.g., Monday 10:30 AM)
  ├── 1. Investor enters limit order on FinTech app (e.g., Buy 100 Infosys @ ₹1,500)
  ├── 2. Broker RMS verifies client margin balance in real time
  ├── 3. Order routed to Exchange Matching Engine (NSE/BSE); matched with seller
  ├── 4. Trade executed; Exchange sends real-time execution confirmation back to broker
  └── 5. End of Day: Broker issues Contract Note detailing trade price, brokerage, STT, and levies

  NIGHT T (Clearing House Processing)
  ├── Clearing Corporation (NCL / ICCL) nets multilateral obligations across all brokers
  └── Net funds pay-in and net securities delivery obligations determined

  DAY T+1 (Settlement Day - e.g., Tuesday)
  ├── 11:00 AM: Pay-in of funds (buyers transfer cash) & securities (sellers debit Demat)
  ├── 01:30 PM: Pay-out of funds to selling broker & pay-out of securities to buying broker
  └── 04:30 PM: Buying investor receives shares directly credited to their CDSL/NSDL Demat account
```

---

## 6. Financial Market Participants

Financial markets aggregate heterogeneous participants with distinct objectives, risk appetites, and capital scales:

1. **Retail Investors:** Individual citizens investing personal savings (max application size in retail IPO quota: ₹2 Lakhs).
2. **High-Net-Worth Individuals (HNIs / Non-Institutional Investors - NII):** Wealthy individuals investing upwards of ₹2 Lakhs per transaction, often utilizing Margin Trading Facilities (MTF).
3. **Domestic Institutional Investors (DIIs):** Indian institutions pooling domestic capital—including Mutual Funds (e.g., SBI MF, HDFC MF), Life Insurance Companies (e.g., LIC), and pension funds (NPS/EPFO).
4. **Foreign Portfolio Investors (FPIs / FIIs):** Sovereign wealth funds, global hedge funds, and foreign pension funds investing foreign capital into Indian markets under SEBI FPI regulations.
5. **Qualified Institutional Buyers (QIBs):** Institutional entities possessing financial expertise to evaluate issues without retail protections (allocated 50% in standard mainboard IPOs).
6. **Proprietary Trading Desks (Prop Desks):** Trading firms deploying their own corporate capital using high-frequency trading (HFT) and algorithmic arbitrage strategies.
7. **Market Makers:** Liquidity providers contractually committed to quoting continuous bid-ask prices to ensure smooth market depth.
