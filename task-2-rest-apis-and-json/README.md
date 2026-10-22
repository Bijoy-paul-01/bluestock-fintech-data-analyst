# REST APIs & JSON: A FinTech Data Analyst's Guide

> **Module 2 Reference & Implementation Guide**  
> *Targeted for Bluestock Fintech Onboarding & Financial Analytics*

---

## 1. What is an API?
An **API (Application Programming Interface)** is a formalized set of protocols, routines, and tools that allows disparate software systems to communicate and exchange data. In financial technology, APIs power everything from live market ticker feeds and broker order execution to payment gateway webhooks and identity verification (KYC).

A **REST (Representational State Transfer) API** adheres to architectural constraints:
* **Statelessness:** Every request contains all information needed to process it; the server retains no client session context.
* **Client-Server Separation:** The client UI and the data storage/backend operate independently.
* **Uniform Interface:** Resources are identified via standard URIs (e.g., `/api/v1/stocks/RELIANCE`).
* **Cacheability:** Responses explicitly label themselves as cacheable or non-cacheable to optimize network efficiency.

---

## 2. HTTP Request Methods

| HTTP Method | Purpose | FinTech Real-World Example | Idempotent? | Safe? |
| :--- | :--- | :--- | :--- | :--- |
| **GET** | Retrieve data from server | Fetching live stock quotes (`GET /api/v1/market/quote?symbol=TCS`) | **Yes** | **Yes** |
| **POST** | Submit data to create a resource | Placing a new buy order (`POST /api/v1/orders`) | **No** | **No** |
| **PUT** | Completely replace an existing resource | Updating complete user profile details (`PUT /api/v1/user/102`) | **Yes** | **No** |
| **PATCH** | Partially update a resource | Modifying the stop-loss price of an open order (`PATCH /api/v1/orders/884`) | **No** | **No** |
| **DELETE** | Remove a resource | Canceling a pending limit order (`DELETE /api/v1/orders/884`) | **Yes** | **No** |

---

## 3. Anatomy of an HTTP Request & Response

```
+-----------------------------------------------------------------------------------+
|                              HTTP Request Breakdown                               |
+-----------------------------------------------------------------------------------+
|  1. Request Line:    GET /api/v3/coins/markets?vs_currency=inr HTTP/1.1           |
|  2. Headers:         Accept: application/json                                     |
|                      Authorization: Bearer eyJhbGciOi...                          |
|                      User-Agent: BluestockAnalyticsClient/1.0                     |
|  3. Query Params:    vs_currency=inr & order=market_cap_desc & per_page=25        |
|  4. Request Body:    (Used in POST/PUT - empty for GET)                           |
+-----------------------------------------------------------------------------------+
                                          |
                                          v (Network Roundtrip)
                                          |
+-----------------------------------------------------------------------------------+
|                              HTTP Response Breakdown                              |
+-----------------------------------------------------------------------------------+
|  1. Status Line:     HTTP/1.1 200 OK                                              |
|  2. Response Headers:Content-Type: application/json; charset=utf-8                 |
|                      Date: Wed, 22 Oct 2026 14:20:00 GMT                          |
|                      RateLimit-Remaining: 29                                      |
|  3. Response Body:   [ { "id": "bitcoin", "current_price": 5820000, ... } ]        |
+-----------------------------------------------------------------------------------+
```

### Standard HTTP Status Codes

| Code Group | Meaning | Examples in FinTech |
| :--- | :--- | :--- |
| **2xx Success** | Request processed successfully | `200 OK` (Data retrieved), `201 Created` (Order submitted) |
| **3xx Redirection** | Action required to complete request | `301 Moved Permanently`, `304 Not Modified` (Cached market feed) |
| **4xx Client Error** | Issue on client side | `400 Bad Request` (Invalid lot size), `401 Unauthorized` (Invalid auth token), `403 Forbidden` (Insufficient margin), `404 Not Found` (Stock ticker doesn't exist), `429 Too Many Requests` (Rate limit hit) |
| **5xx Server Error** | Server-side execution failure | `500 Internal Server Error` (Database crash), `503 Service Unavailable` (Exchange connection down) |

---

## 4. The JSON Format (JavaScript Object Notation)
**JSON** is the de facto lightweight, human-readable data-interchange format for web APIs.

### Key Characteristics:
* **Key-Value Pairs:** Keys are enclosed in double quotes (`"symbol": "INFY"`).
* **Supported Data Types:**
  * String (`"Tata Consultancy Services"`)
  * Number (`3850.50` or `100`)
  * Boolean (`true` or `false`)
  * Array (`["NSE", "BSE"]`)
  * Object (nested JSON structure)
  * `null` (empty value)

### Sample Financial JSON Payload:
```json
{
  "status": "success",
  "exchange": "NSE",
  "quote": {
    "symbol": "TCS",
    "name": "Tata Consultancy Services Limited",
    "last_price": 3925.40,
    "day_high": 3950.00,
    "day_low": 3910.15,
    "volume": 1420580,
    "circuit_limits": {
      "upper": 4317.90,
      "lower": 3532.90
    },
    "is_fno_enabled": true
  }
}
```

---

## 5. Query Parameters vs. Path Parameters

* **Path Parameters:** Identify a specific resource hierarchically.
  * Example: `https://api.bluestock.in/v1/stocks/TCS` (`TCS` is the unique resource identifier).
* **Query Parameters:** Filter, paginate, or sort resources without altering the endpoint identity.
  * Example: `https://api.bluestock.in/v1/screener?sector=IT&pe_max=30&sort=market_cap_desc`
  * Format: Begins with `?`, separated by `&`, using `key=value` syntax.

---

## 6. Authentication Basics in Modern FinTech APIs

1. **Public / No Auth:** Endpoints open for general discovery (e.g., market holiday schedules).
2. **API Keys:** A unique token passed in headers (e.g., `X-API-KEY: blk_live_948f921`). Common for B2B data vendors.
3. **HTTP Basic Auth:** Username and password encoded in Base64 (`Authorization: Basic dXNlcjpwYXNz`). Not recommended for production without HTTPS.
4. **Bearer Token (JWT - JSON Web Tokens):** Client submits credentials once, receives a cryptographically signed token containing expiry and permissions, passed in header:
   ```http
   Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   ```
5. **OAuth 2.0:** Standard protocol for delegated authorization. Enables third-party applications to act on behalf of a user without seeing their raw password (e.g., Zerodha Kite Connect login or Bluestock multi-broker integration).

---

## 7. API Testing Tools: Postman & Bruno

* **Postman:** Leading collaborative API testing tool with environment variables, automated test scripts, mock servers, and visualizers.
* **Bruno:** Fast, lightweight, open-source, Git-friendly alternative that stores collections directly as plain text files in your local codebase repository.

### Imported Collection:
This project includes a ready-to-run API collection:
`task-2-rest-apis-and-json/postman/bluestock_api_collection.json` containing endpoints, headers, query parameters, and validation scripts.

---

## 8. Automated Script Execution
To execute the automated Python data pipeline:
```bash
python task-2-rest-apis-and-json/api_fetch_and_convert.py
```
This fetches real-time market data, serializes the raw JSON to `data/market_data.json`, and exports an enriched tabular dataset to `data/market_data.csv`.
