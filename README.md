# n8n Automation Portfolio

A collection of **17 n8n workflows** built by **Rakshit Dagar** — Data Science & AI undergraduate at IIM Sambalpur, based in **Rewari, Haryana**.

These workflows cover AI agents and RAG, lead qualification and scoring, cold-email personalization at scale, appointment booking and reminders, e-commerce inventory sync, invoice reconciliation, recruitment screening, support-ticket triage, content repurposing, social publishing, daily digests, and voice-to-CRM. They are built with LangChain, OpenAI, Google Gemini, Groq, Moonshot Kimi, Pinecone, Airtable, Slack, Gmail, Google Sheets/Drive/Calendar/Tasks/Docs, Stripe, Shopify, Amazon SP-API, Serper, SerpApi, NewsData.io, and Fireflies.

## Projects

| # | Project | What it does | Key services |
|---|---------|--------------|--------------|
| 1 | [Abandoned Cart Recovery](./abandoned-cart-recovery) | Waits 24h after cart abandonment, then sends a Gemini-written recovery email if payment is still pending | Webhook, Gemini 2.5 Flash, Gmail |
| 2 | [AI Customer Support Agent (RAG)](./ai-customer-support-rag) | Ingests FAQ docs into Pinecone and answers support emails from the knowledge base, with Slack escalation | Pinecone, OpenAI, Gmail, Slack, Google Drive |
| 3 | [AI-powered Lead Qualification + Scoring](./ai-lead-qualification-scoring) | Scores Typeform leads as hot/cold via Gemini; hot leads to Slack, cold leads get a nurture email | Gemini, Google Sheets, Slack, Gmail |
| 4 | [AI-powered Outbound Cold Email Personalization at Scale](./ai-cold-email-personalization-at-scale) | Scrapes prospect sites, writes personalized cold emails, and follows up based on reply status | OpenAI, Gmail, Google Sheets |
| 5 | [Automated Reminder Booking + Reminder System](./automated-reminder-booking) | Books intro calls, researches clients via SerpApi, scores against ICP, blocks prep time on Calendar, notifies via Slack/Gmail | Gemini, SerpApi, Google Docs, Slack, Calendar, Gmail |
| 6 | [Client's Info and First Mail](./clients-info-and-first-mail) | Webhook intake → Groq writes a customised first email → logged to Sheets → sent via Gmail | Groq, Google Sheets, Gmail |
| 7 | [Content Calendar](./content-calendar) | Publishes calendar rows to Twitter, Instagram, and LinkedIn based on platform | Google Sheets, Twitter, Instagram, LinkedIn |
| 8 | [Daily Email Digest Bot](./daily-email-digest-bot) | Daily email merging calendar events, tasks, open-meteo weather (Rewari), and NewsData.io news | Gemini, Gmail, Calendar, Tasks, open-meteo, NewsData.io |
| 9 | [E-commerce Inventory Sync](./e-commerce-inventory-sync) | Scheduled sync of Shopify and Amazon inventory, logged and pushed back via Google Sheets | OpenAI, Shopify, Amazon SP-API, Google Sheets |
| 10 | [Invoice + Expenses Reconciliation](./invoice-expenses-reconciliation) | Matches Stripe charges to invoices in Sheets; flags mismatches to Slack | Stripe, OpenAI, Google Sheets, Slack |
| 11 | [Mail Prioritiser](./mail-prioritiser) | Prioritizes inbound Gmail and auto-applies labels | Groq, Gmail |
| 12 | [Multi-agent Research + Report Workflow](./multi-agent-research-report) | Chat-triggered company research via Serper, summarized and formatted into a Google Doc + PDF | Serper, OpenAI, Moonshot Kimi, Google Drive |
| 13 | [Multi-platform Review Monitor](./multi-platform-review-monitor) | Tags Google/Trustpilot/Zomato reviews with Gemini; stores positives, alerts negatives on Slack | Gemini, Google Sheets, Slack |
| 14 | [Multi-step Content Repurposing Pipeline](./multi-step-content-repurposing-pipeline) | One transcript → LinkedIn post, Twitter thread, and email newsletter, each human-approved on Slack | OpenAI, Slack |
| 15 | [Recruitment Pipeline Automation](./recruitment-pipeline-automation) | Screens resumes from a Drive folder; accepts/rejects/routes to manual review with emails and Slack | Google Drive, Gemini, Gmail, Sheets, Slack |
| 16 | [Support Ticket Triage + AI Drafted Response](./support-ticket-triage-ai-drafted-response) | Drafts support-email replies from a knowledge base with human-in-the-loop Slack approval before sending | Gemini, Google Docs, Gmail, Slack |
| 17 | [Voice-to-CRM Pipeline](./voice-to-crm-pipeline) | Transcribes Fireflies meetings, summarizes with OpenAI, upserts to Airtable | OpenAI, Fireflies, Slack, Airtable |

Two workflows ship in two parts:
- **AI Customer Support Agent (RAG)**: `ingestion/` (loads docs into Pinecone) and `query/` (answers emails).
- **AI-powered Outbound Cold Email Personalization at Scale**: `first-email/` (personalized first outreach) and `sequencer-and-reply/` (scheduled follow-ups).

## Repo structure

```
n8n-automation-portfolio/
├── README.md
├── LICENSE
├── .gitignore
├── assets/                       # reference images (AI-ML roadmap, dashboard)
├── abandoned-cart-recovery/
│   ├── README.md
│   ├── Abandoned Cart Recovery.json
│   └── Abandoned Cart Recovery.PNG
├── ai-customer-support-rag/
│   ├── README.md
│   ├── ingestion/ (...json, ...PNG)
│   └── query/ (...json, ...PNG)
├── ... (one folder per workflow, each with README.md + workflow .json + screenshot)
```

Every project folder contains its own `README.md` explaining the workflow step by step, plus the n8n workflow export (`.json`) and a canvas screenshot.

## Quick start

1. **Install n8n** — `npm install -g n8n` (or use n8n Desktop/Cloud).
2. **Import a workflow** — in n8n, go to Workflows → Import and select the project's `.json` file.
3. **Configure credentials** — each node that connects to a service (Gmail, Google Sheets, Pinecone, etc.) needs your own credentials; connection IDs in the exports are placeholders.
4. **Replace placeholder IDs** — spreadsheet IDs, sheet names, webhook paths, Pinecone index, Drive folder IDs, document URLs, Slack channels, etc.
5. **Save and activate** — then test with a manual execution.

## Credentials you will need

Gmail · Google Sheets · Google Drive · Google Calendar · Google Tasks · Google Docs · OpenAI API · Google Gemini API · Groq API · Moonshot Kimi API · Pinecone · Airtable · Slack · Stripe · Twitter · Instagram · LinkedIn · Serper API · SerpApi · NewsData.io API · Fireflies

open-meteo weather is key-free.

## About

Built by Rakshit Dagar — B.S. Data Science & AI, IIM Sambalpur (Roll: 2026BSDSAI068), Rewari, Haryana. Skills: Python, pandas, NumPy, Matplotlib, Seaborn, scikit-learn, LangChain, n8n, GenAI and automation.

Contact: rakshitdagar15@gmail.com · +91 74949 36444  
GitHub: github.com/bigfoot15agency · X: x.com/bigfoot15agency · LinkedIn: linkedin.com/in/rakshit-dagar-2208a4421

## License

MIT — see LICENSE.
