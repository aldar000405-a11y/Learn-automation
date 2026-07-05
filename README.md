## What is this repository?

This is your **practical workspace** for the apprenticeship. It contains the n8n workflows, database schemas, and configuration templates you build during the learning phases (Phases 1–6). Everything here is designed to be imported, studied, modified, and extended — not copy-pasted blindly.

Think of it as a **living toolbox**: new workflows are added as the curriculum grows. You watch the repo, you pull the update, you keep learning.

---

## Repository Structure

Drop files into these folders. The README never needs editing when you add something new.

```
n8n-automation-workflows/
├── learning-workflows/          , Workflows from Phases 1–6 (import → study → modify)
│   ├── phase-01-foundation/
│   ├── phase-02-ai-integration/
│   ├── phase-03-whatsapp-agent/
│   └── phase-04-voice-ai/
│
├── schemas/                     , SQL files for Supabase/PostgreSQL tables
│
├── boilerplates/                , Empty workflow skeletons (sub-workflows, error handlers)
│
├── config-templates/            , CSV, JSON, and environment variable templates
│
└── docs/                        , Render deployment guides, naming convention cheatsheets
```

> **Portfolio Projects (Phase 7) and Capstone Projects (Phase 8) are NOT stored here.**  
> You build those from scratch inside your own n8n instance, with the coach guiding you step by step. Your portfolio belongs to you alone.

---

## How to use any workflow in this repo

### 1. Import
1. Open your n8n instance (self-hosted on Render or cloud).
2. Go to **Workflows** → **Import from File**.
3. Select any `.json` file from the `learning-workflows/` folder.
4. n8n recreates the full workflow — nodes, connections, and layout.

### 2. Connect credentials
Look for red dots on nodes. Click each node → **Credentials** → select or create your credential.

**The curriculum uses only free APIs:**
- Google Gemini API ([aistudio.google.com](https://aistudio.google.com))
- Groq API ([console.groq.com](https://console.groq.com))
- Supabase PostgreSQL ([supabase.com](https://supabase.com))
- Slack free workspace ([slack.com](https://slack.com))
- Google Sheets / Gmail / Calendar (OAuth via Google Cloud Console)
- WAHA (self-hosted on Render)
- VAPI ([vapi.ai](https://vapi.ai))
- Stripe test mode ([stripe.com](https://stripe.com))

> Full setup instructions (exact URLs, exact clicks, the mistake everyone makes) are inside the apprenticeship curriculum. This repo holds the workflow files only.

### 3. Activate and test
1. Click **Save**, then **Activate** (for webhook workflows).
2. Send a test payload using [hoppscotch.io](https://hoppscotch.io) or the built-in test button.
3. Verify the result in your Slack channel, Supabase table, or Google Sheet.

---

## How the learning phases map to this repo

| Phase | Topic | What you'll find in this repo |
|-------|-------|------------------------------|
| **Phase 1** | n8n internals, HTTP, JavaScript, webhooks, error handling, PostgreSQL | Foundation workflows + SQL schemas |
| **Phase 2** | Gemini & Groq AI, prompt engineering, AI agents, memory | AI classifier and agent workflows |
| **Phase 3** | WhatsApp bot with WAHA, booking, FAQ, memory | WhatsApp send/receive patterns |
| **Phase 4** | Voice AI with VAPI, RAG, pgvector | Voice function call templates + RAG queries |
| **Phase 5** | Freelance skills (pricing, proposals, scope) | Config templates for client-managed values |
| **Phase 6** | Payments, reconciliation, dunning | Stripe webhook boilerplates + SQL tables |

**Phase 7 (Portfolio Projects)** and **Phase 8 (Capstone Projects)** are built entirely by you in your own n8n instance, guided by the coach. They are not downloadable files — they are the proof that you can build from scratch.

---

## Living Repository — Free Lifetime Updates

This repo is **not a one-time download**. Watch it (GitHub → Watch → All Activity) and pull updates as the curriculum expands.

**What gets added here:**
- New learning workflows as each phase is completed
- Updated SQL schemas when new tables are introduced
- Revised boilerplates when best practices change
- New config templates for tools added to the curriculum

**What does NOT get added here:**
- Portfolio project solutions (you build those)
- Capstone project solutions (you deliver those to clients)
- Loom scripts or Upwork pitches (you write those with the coach)

No re-purchase. No extra fees. One buy, all future learning materials.

---

## Production Rules (apply to everything you build)

### Naming Convention
Every node must follow: `ACTION — Subject — Source`  
Example: `GET — Weather Data — OpenMeteo API` instead of default `HTTP Request`.

The coach will reject any workflow with unnamed nodes. Rename immediately after adding.

### Security
- **Never commit real API keys.** All workflows here use n8n credential placeholders.
- Store secrets in **Render environment variables**, never inside nodes.
- Production webhooks require signature verification (Stripe, HMAC via Cloudflare Worker).

### Idempotency
Any workflow that receives a webhook must check for duplicates before acting. The schemas folder includes the `processed_events` pattern. Use it.

### Error Handling
Every external API call needs a path for: 400, 401, 429, 500. If a workflow fails at 2am, someone must know before the client calls.

---

## Support

**Curriculum & setup questions:**  
Email support included for **14 days** after purchase. Response within 24 hours on business days.

**Bug reports:**  
Open an issue. Include: workflow name, n8n version, exact error message, execution log screenshot.


---

## License

These learning materials are provided as part of the n8n AI Automation Engineering apprenticeship.  
**For personal use by the purchaser only.** Redistribution, resale, or public sharing outside the intended learning context is not permitted.
