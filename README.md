# Saathi

**An AI companion that walks you through every loan, insurance policy and payment, in your own language.**

Built by **Team Eraya** for the Paytm Build for India AI Hackathon, Bengaluru.
Track 2: AI-Powered Financial Journeys.

**Team:** Janapati Thanu Sree · Kavyashri K R

---

## The problem

Financial journeys are built for paperwork, not people. Customers hit four walls:

- **Jargon:** terms like APR, KFS, exclusions and waiting periods go unexplained.
- **Forms:** every lender and insurer asks for the same details again.
- **Rejections:** a name mismatch or a missing document sinks an application or claim, with no reason given.
- **Language:** journeys assume English and confidence.

## What Saathi does

| Journey | What Saathi does |
|---|---|
| **Lend** | Finds the right loan, explains its key fact statement (KFS) by voice, pre-checks the application before it is sent |
| **Insure** | Compares cover in plain words, flags exclusions upfront, guides every claim step by step |
| **Pay** | Sets up EMIs and AutoPay, nudges before due dates, raises disputes for failed payments |

**How a journey flows:** Ask → Understand → Share → Pre-check → Finish and stay.

## Tech stack (planned)

- **App:** React PWA (chat and voice), WhatsApp channel
- **Voice:** Bhashini for Indian-language speech
- **AI:** LLM agent with tool use, RAG over KFS and policy documents, document AI (OCR and extraction), rejection-risk model, PII redaction guardrails
- **Backend:** Python, FastAPI, PostgreSQL with pgvector, Redis, consent and audit log
- **Rails:** Aadhaar eKYC, DigiLocker, Account Aggregator, UPI

## Getting started

> Status: hackathon prototype. Update the commands below to match the code in this repo.

### Prerequisites

- Python 3.11+
- Node.js 20+
- PostgreSQL 15+ with the `pgvector` extension
- An API key for your LLM provider

### Setup

```bash
git clone https://github.com/<your-username>/saathi.git
cd saathi

# Backend
cd backend
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env             # then add your keys
uvicorn app.main:app --reload

# Frontend (in a new terminal)
cd frontend
npm install
npm run dev
```

Open http://localhost:5173 (frontend) and http://localhost:8000/docs (API).

### Environment variables

| Variable | Purpose |
|---|---|
| `LLM_API_KEY` | Key for the LLM provider |
| `DATABASE_URL` | PostgreSQL connection string |
| `REDIS_URL` | Redis connection string |

## Privacy

Every data pull is consent-based, logged and revocable by the customer. Personal data is redacted before it reaches the model.

## Business model

Free for customers. Partners pay for outcomes: per completed application or claim, a platform licence, distribution commission, and journey analytics.

## Team

**Team Eraya**

- Janapati Thanu Sree
- Kavyashri K R
