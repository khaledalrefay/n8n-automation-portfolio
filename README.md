# n8n Automation Portfolio

Workflow automation systems built with **n8n**, AI agents, and self-hosted
infrastructure. Each project ships the full workflow export, an architecture
diagram, and notes on the design decisions behind it.

**Khaled Al-Refay** — AI Workflow Automation Developer
[LinkedIn](#) · [Email](mailto:Khaled.refay98@gmail.com)

---

## Projects

### [Smart Retail Assistant](./smart-retail-assistant/)

A Telegram-operated ledger for a small retail shop. The owner records sales,
debt payments, and pricing by **typing or sending a voice note in Arabic** — an
AI agent interprets the request and writes to the right place. A scheduled job
sends a closing report every night.

`33 nodes` · `2 triggers` · `10 AI agent tools` · `6 routed paths`

**Stack:** n8n · Telegram Bot API · OpenRouter (LLM + Whisper transcription) ·
Google Sheets · schedule triggers

---

### [AI Course Manager](./ai-course-manager/)

A WhatsApp system that runs the full learner lifecycle for an online course:
enrollment onboarding, conversational support, payment follow-up, and lecture
reminders. WhatsApp connectivity comes from a **self-hosted Evolution API
instance on Docker** rather than a paid gateway.

`27 nodes` · `4 independent workflows` · `4 triggers`

**Stack:** n8n · WhatsApp via self-hosted Evolution API (Docker) ·
OpenRouter · Google Forms · Google Sheets

---

## Repository layout

```
.
├── smart-retail-assistant/
│   ├── README.md          project write-up and architecture
│   ├── workflow.json      sanitized n8n export
│   └── screenshots/
├── ai-course-manager/
│   ├── README.md
│   ├── workflow.json
│   └── screenshots/
└── scrub_n8n.py           sanitizer used before publishing any export
```

## Running a workflow

1. Import `workflow.json` into your n8n instance.
2. Create your own credentials — the exports carry **no** credential data.
3. Replace every `YOUR_SHEET_ID`, `YOUR_FORM_ID`, `YOUR_API_KEY_HERE`, and
   `REDACTED` placeholder with your own values.
4. Recreate the Google Sheets tabs described in each project's README.


## License

MIT — see [LICENSE](./LICENSE).
