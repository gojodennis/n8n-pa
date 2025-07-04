# Productivity Assistant Bot

Minimal personal assistant. Telegram-based interface.  
Handles email, tasks, events — fast and fluid.

---

## 🧭 What It Does

> Ask. It acts.

Via Telegram, you can:
- Summarize recent emails
- Add or check tasks (Google Tasks)
- Schedule or view calendar events (Google Calendar)
- Talk in plain language — Gemini interprets

---

## ⚙️ Stack

- **Telegram Bot API** – Messaging layer
- **Gemini Pro (Google LLM)** – Context, understanding
- **Gmail API** – Email fetch & parse
- **Google Tasks API** – Personal to-dos
- **Google Calendar API** – Scheduling
- **n8n** – Orchestration and automation

---

## ▶️ Usage

1. Clone this repo.
2. Create `.env` with:
    ```
    TELEGRAM_TOKEN=
    GEMINI_API_KEY=
    GMAIL_CREDENTIALS_JSON=
    GOOGLE_TASKS_CREDENTIALS_JSON=
    GOOGLE_CALENDAR_CREDENTIALS_JSON=
    ```
3. Set up Google Cloud project (OAuth2 access).
4. Deploy with [n8n](https://n8n.io) self-hosted or cloud.

---

## 🔁 Flow


- Gemini parses request: "What are my tasks today?"
- n8n routes to appropriate service
- Response sent back via Telegram

---

## 📦 Dependencies

- `@google/generative-ai`
- `googleapis`
- `node-telegram-bot-api`
- `axios`

---

## 🔒 Auth

All Google services use OAuth2. Tokens are refreshed automatically.  
Keep `.env` and `tokens/` outside of version control.

---

## 📁 Structure

- `/workflow.json` – Import into n8n
- `/src/` – Service modules (Gmail, Calendar, etc.)
- `/docs/` – API scopes, OAuth setup

---

## ⚠️ Caveats

- Rate limits apply (especially Gmail).
- Gemini might infer wrong intent — prompt carefully.
- Telegram replies are plain text (no rich UI yet).

---

## 🚧 Next Steps

- Integrate Google Drive support
- Enable recurring reminders
- Add voice commands (via Whisper + Telegram voice)
- UI layer (React or Tauri, maybe)

---

## 🐚 License

MIT.  

---
