# Email to Google Sheets Automation

Automatically captures incoming Gmail emails and logs them to Google Sheets in real-time using n8n.

## How it works

1. **Email Trigger (IMAP)** — monitors Gmail inbox for new emails
2. **Google Sheets** — appends each email as a new row (Date, From, Subject, Body)

## Tech Stack

- [n8n](https://n8n.io) — workflow automation
- Docker — containerization
- AWS EC2 — 24/7 hosting
- Gmail IMAP — email trigger
- Google Sheets API — data storage

## Setup

### 1. Clone the repo
```bash
git clone https://github.com/Saher-15/email-to-sheets-automation.git
cd email-to-sheets-automation
```

### 2. Configure environment
```bash
cp .env.example .env
```
Edit `.env` with your credentials:
```
N8N_USER=admin
N8N_PASSWORD=your_password_here
```

### 3. Start n8n
```bash
docker compose up -d
```

### 4. Open n8n
Go to `http://localhost:5678` and import `workflow.json`

### 5. Configure credentials
- **Gmail IMAP** — use an app password (requires 2FA)
- **Google Sheets** — use a service account JSON key

## Architecture

```
Gmail Inbox → IMAP Trigger → Google Sheets
```
