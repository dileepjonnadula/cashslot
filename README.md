# Cash Slot

A demo service for booking branch counter cash deposits and withdrawals. It includes a customer web UI, staff dashboard, receipts, cash planning, and a FastAPI API. The service does not post transactions to a bank's core banking system.

## Source

[Download the project source](./cashslot-source.zip). The archive contains the app, tests, configuration examples, and full setup notes.

## Run locally

Extract the archive, open a terminal in the extracted folder, and run:

```powershell
pip install -r requirements.txt
uvicorn app.main:app --port 8000
```

Then open `http://localhost:8000/ui`. Demo accounts and test data are described in the included README.

## Deploy a public demo

This is a FastAPI application, so GitHub Pages cannot host the running app. A Render Blueprint is provided in `render.yaml`. In Render, create a new Blueprint from this repository; after deployment, open the service URL and add `/ui`.

## Demo safety

This public demo uses mock integrations, demo credentials, and temporary SQLite storage. Anyone can access a deployed demo, and its data may reset when it restarts. Use fake data only. Do not enter real customer information, connect real bank integrations, or use it for banking operations. Production use requires bank-approved infrastructure, persistent storage, security review, and compliance approval.
