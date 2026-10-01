<<<<<<< HEAD
 LedgerLens AI — Intelligent Payment Reconciliation & Risk Detection

> AI-assisted payment reconciliation platform for matching merchant orders, payment gateway transactions, and bank settlements while detecting mismatches, anomalies, and unresolved payment issues.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![FastAPI](https://img.shields.io/badge/FastAPI-Backend-green)
![React](https://img.shields.io/badge/React-Frontend-61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-Frontend-blue)
![Machine Learning](https://img.shields.io/badge/ML-Anomaly%20Detection-orange)
![FinTech](https://img.shields.io/badge/Domain-FinTech-purple)

---

## 🚀 Overview

Payment data is often distributed across multiple systems:

- Merchant order records
- Payment gateway transactions
- Bank settlement records

When these systems contain different references, amounts, fees, dates, or settlement information, identifying the actual problem can become difficult.

**LedgerLens AI** brings these records together into a single reconciliation workflow.

The system:

- Matches related payment records
- Identifies reconciliation mismatches
- Detects suspicious or anomalous transactions
- Classifies payment exceptions
- Tracks confidence for reconciliation results
- Investigates unresolved payment issues using AI
- Provides an interactive dashboard for reviewing results

---

## 🎯 Problem Statement

Consider a payment that appears differently across three systems:

```text
Merchant Order
      │
      │ Gross Amount
      ▼
Payment Gateway
      │
      │ Fees / Net Amount
      ▼
Bank Settlement
      │
      │ Payout / Settlement
      ▼
LedgerLens AI

A transaction may be:

Correctly matched
Missing from one system
Recorded with a different amount
Affected by fees
Refunded
Duplicated
Delayed during settlement
Difficult to classify automatically

LedgerLens AI helps identify these cases and presents the evidence in one place.

✨ Key Features
🔄 Payment Reconciliation

LedgerLens compares payment information across:

Merchant ledger
Payment gateway transactions
Bank settlements

The reconciliation engine evaluates relationships between records instead of treating each file independently.

🚨 Anomaly & Risk Detection

The system can identify payment issues such as:

Duplicate transactions
Missing settlement records
Amount mismatches
Fee mismatches
Refund-related discrepancies
Unresolved payment records
Unexpected transaction relationships

Each detected issue can be surfaced as an exception for further investigation.

🤖 AI-Assisted Investigation

Not every payment exception can be resolved using deterministic matching rules.

For unresolved cases, LedgerLens can use an AI investigation layer to examine available transaction evidence and produce an explanation.

The AI layer is intended to assist investigation rather than blindly override reconciliation results.

Deterministic Reconciliation
          │
          ├── Resolved ───────────────► Result
          │
          └── Unresolved
                  │
                  ▼
           AI Investigation
                  │
                  ▼
          Explanation / Review
📊 Interactive Dashboard

The React dashboard provides a visual interface for:

Reconciliation results
Transaction records
Payment exceptions
Risk indicators
Settlement information
Evidence and investigation results

The dashboard is designed to make payment operations easier to inspect and understand.

🏗️ Architecture
                 ┌──────────────────────┐
                 │   Merchant Orders    │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │                      │
                 │   LedgerLens Engine  │
                 │                      │
                 └──────────┬───────────┘
                            │
              ┌─────────────┼─────────────┐
              │             │             │
              ▼             ▼             ▼
        Payment Gateway   Bank Data    Reconciliation
              │                           │
              │                           ▼
              │                    Risk Detection
              │                           │
              └──────────────┬────────────┘
                             ▼
                      Unresolved Cases
                             │
                             ▼
                      AI Investigation
                             │
                             ▼
                      Review Dashboard
🛠️ Technology Stack
Backend
Python
FastAPI
REST APIs
Pandas
Frontend
React
TypeScript
Vite
Tailwind CSS
AI / ML
Machine Learning
Anomaly Detection
LLM-assisted investigation
Testing
Pytest
Automated API and reconciliation tests
Deployment / Infrastructure
Docker
GitHub Actions
GitHub Pages for the frontend workflow
🔍 Reconciliation Workflow
1. Load Payment Data

The system accepts structured payment data representing different stages of the payment lifecycle.

2. Normalize Records

Records are processed into a consistent format so that they can be compared across sources.

3. Match Transactions

LedgerLens evaluates relationships between merchant, gateway, and bank records.

4. Validate Results

Potential matches are checked using transaction attributes such as:

Amount
Payment reference
Settlement information
Dates
Transaction relationships
5. Detect Exceptions

Records that cannot be confidently reconciled are classified as exceptions.

6. Investigate

Selected unresolved cases can be passed to the AI investigation layer.

7. Review

The dashboard presents the reconciliation output and detected issues.

📁 Project Structure
LedgerLens-AI/
│
├── data/
│
├── datasets/
│
├── docs/
│
├── scripts/
│
├── src/
│   ├── app.py
│   ├── analysis.py
│   ├── core.py
│   ├── matcher.py
│   ├── assignment.py
│   ├── taxonomy.py
│   ├── report.py
│   └── ...
│
├── tests/
│
├── web/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── vite.config.ts
│
├── Dockerfile
├── requirements.txt
├── pyproject.toml
└── README.md
⚙️ Running Locally
Backend

Clone the repository:

git clone https://github.com/Ugesh123/LedgerLens-AI-Intelligent-Payment-Reconciliation-Risk-Detection.git

cd LedgerLens-AI-Intelligent-Payment-Reconciliation-Risk-Detection

Install Python dependencies:

pip install -r requirements.txt

Start the FastAPI application:

python -m uvicorn app:app --app-dir src --reload

The API will be available at:

http://localhost:8000

FastAPI documentation:

http://localhost:8000/docs
💻 Frontend

Install frontend dependencies:

cd web
npm install

Start the development server:

npm run dev

For a production build:

npm run build
🧪 Testing

Run the test suite:

python -m pytest tests/ -q

The project includes tests covering reconciliation logic, APIs, detection behaviour, and data integrity.

🔌 API

The backend exposes REST endpoints for working with reconciliation data.

Example API capabilities include:

GET  /api/v1/health
GET  /api/v1/datasets
POST /api/v1/datasets/{name}
POST /api/v1/sample
POST /api/v1/reconcile
GET  /api/v1/taxonomy

The API is designed so that the reconciliation engine can be used independently from the dashboard.

💡 Design Approach

LedgerLens follows a simple principle:

Use deterministic rules for financial verification and AI for investigation.

Financial reconciliation should not depend entirely on an LLM.

Therefore:

Rules / Matching
       │
       ▼
Validation
       │
       ├── Confident match ──► Reconciled
       │
       └── Unresolved
                │
                ▼
        AI-assisted analysis
                │
                ▼
          Human review

This approach keeps the core reconciliation process predictable while still using AI where it adds value.

🎯 Use Cases

LedgerLens AI can support workflows such as:

Payment operations
Merchant settlement monitoring
Finance reconciliation
Payment exception investigation
Transaction anomaly detection
FinTech operations analytics
Payment data quality monitoring
🔮 Future Improvements

Planned improvements include:

Real payment gateway integrations
PostgreSQL-based transaction storage
Real-time payment monitoring
Improved anomaly detection models
Risk scoring for transactions
Automated reconciliation reports
Role-based dashboards
Notification system for high-risk exceptions
Better explainability for detected anomalies
📌 Project Status

LedgerLens AI is an actively developed FinTech project focused on payment reconciliation, anomaly detection, backend engineering, and AI-assisted financial operations.

The current implementation uses structured datasets and a local reconciliation workflow. Real-world payment-provider integration and production-scale infrastructure are future extensions.

👨‍💻 Author
Ugesh Yada

B.Tech Computer Science Engineering — 2026
=======
LedgerLens AI — Intelligent Payment Reconciliation \&

Risk Detection

An adapted and extended payment reconciliation project for studying transaction matching, reconciliation workflows,

exception detection, and AI-assisted investigation.

Based on the original Three-Way Financial Reconciliation Engine by Rahul Paul.

Overview

LedgerLens AI reconciles payment records across multiple financial sources and identifies mismatches, unresolved

transactions, and potential risk conditions.

The project focuses on:

• Payment reconciliation

• Transaction matching

• Exception detection

• Investigation workflows

• Risk-oriented analysis

• AI-assisted investigation

• Deterministic verification

Key Capabilities

Three-way reconciliation

The system compares transaction information across:

1\. Merchant ledger 2. Payment gateway report 3. Bank statement

It attempts to match corresponding records and classifies differences for further investigation.

Exception detection

Transactions can be surfaced when records disagree across sources, including:

• Missing transactions

• Amount mismatches

• Status mismatches

• Duplicate records

• Timing-related differences

• Other reconciliation exceptions

AI-assisted investigation

AI can be used to assist with investigation and explanation of reconciliation exceptions.

The core design principle is:

Model proposes; deterministic code verifies.

AI-generated suggestions should therefore be treated as investigative assistance rather than as the final source of truth.

Architecture

The project is organized around a Python reconciliation engine with a web interface.

High-level flow:

Merchant Ledger \\ \\ Reconciliation Engine / / Payment Gateway

Bank Statement | v Exception Detection | v Investigation / Risk Analysis | v Report / Dashboard

Technology Stack

Backend

• Python

• FastAPI

• Pydantic

• Deterministic reconciliation logic

Frontend

• React

• TypeScript

• Vite

• Tailwind CSS

AI / Investigation

• LLM-assisted investigation

• Rule-based validation

• Structured reconciliation results

Testing

• Pytest

• API tests

• Reconciliation tests

Project Structure

LedgerLens-AI/

nnn src/

n nnn agent.py

n nnn analysis.py

n nnn app.py

n nnn core.py

n nnn evaluate.py

n nnn investigate.py

n nnn llm.py

n nnn matcher.py

n nnn narration.py

n nnn report.py

n nnn tools.py

n

nnn web/

n nnn src/

n nnn public/

n nnn package.json

n nnn vite.config.ts

n

nnn datasets/

nnn data/

nnn tests/

nnn scripts/

nnn ARCHITECTURE.md

nnn DECISIONS.md

nnn LICENSE

nnn README.md

Running Locally

Backend

Create and activate a Python virtual environment, then install dependencies:

pip install -r requirements.txt

Run the application:

uvicorn src.app:app --reload

Frontend

Navigate to the web directory:

cd web

npm install

npm run dev

The frontend can then be opened through the local Vite development server.

Reconciliation Workflow

A typical reconciliation flow is:

1\. Load transaction data from the relevant sources. 2. Normalize transaction fields. 3. Match records using deterministic rules.

4\. Identify unmatched or conflicting records. 5. Classify reconciliation exceptions. 6. Perform additional investigation where

required. 7. Generate reconciliation results and reports. 8. Review risk-oriented findings.

API

The backend exposes API functionality for working with reconciliation data and investigation workflows.

The exact endpoints and request/response formats are implemented in `src/app.py`.

Dashboard

The web application provides a visual interface for reviewing reconciliation results and investigating exceptions.

The dashboard is intended to make financial discrepancies easier to inspect and understand.

Testing

Run the Python test suite with:

pytest

Tests cover important application and reconciliation behavior.

Design Principles

Deterministic verification

Financial reconciliation should rely on deterministic rules for final verification wherever possible.

Explainability

Reconciliation results should be understandable and traceable back to the underlying transaction records.

AI as an assistant

AI can help summarize, investigate, and explain exceptions, but deterministic validation remains important for financial

workflows.

Exception-first workflow

The system focuses attention on records that require investigation rather than treating every transaction as equally important.

Limitations

This project is intended for engineering study, experimentation, and demonstration.

It should not be treated as a production financial reconciliation system without additional work around:

• Security

• Authentication and authorization

• Data privacy

• Audit controls

• Production data validation

• Financial compliance

• Observability

• Reliability

• Operational monitoring

• Large-scale performance



>>>>>>> 719d72d (Rebrand project as LedgerLens AI)
