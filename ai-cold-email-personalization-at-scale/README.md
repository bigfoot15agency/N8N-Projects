# AI-powered Outbound Cold Email Personalization at Scale

Scrapes prospect websites, writes personalized cold emails with AI, and sends follow-up emails based on reply status.

## What it does

Part 1 watches a Google Sheet for new prospects, scrapes their website, uses an AI agent to extract flagged issues, and sends a personalized cold email. Part 2 runs on a schedule, checks email threads for replies, drafts AI follow-ups, and updates the sheet status.

## Part 1 - First Email

1. Google Sheets Trigger - triggers when a prospect row is added.
2. Website Scrapper - HTTP request to the prospect website URL.
3. HTML - extracts HTML content.
4. AI Agent - OpenAI agent extracts issues worthy of flagging.
5. Structured Output Parser - parses email, email_subject, email_body, reason.
6. Update row in sheet - writes results back to Google Sheets.
7. Sending Cold Email - sends the personalized email via Gmail.

## Part 2 - Sequencer and Reply

1. Schedule Trigger - runs on a schedule.
2. Get row(s) from sheet - fetches prospects from Google Sheets.
3. Get a thread - retrieves the Gmail thread.
4. AI Agent - generates a follow-up based on the thread snippet.
5. Sending a Follow-Up Email - replies in the Gmail thread.
6. Mark Status as Replied / Updating Status - updates the sheet.

## Nodes & services

Google Sheets Trigger, HTTP Request, HTML, LangChain Agent (OpenAI), Structured Output Parser, Gmail, Schedule Trigger.

## Files

- first-email/AI-powered Outbound Cold Email Personalization at Scale (First Email).json
- first-email/AI-powered Outbound Cold Email Personalization at Scale (First Email).PNG
- sequencer-and-reply/AI-powered Outbound Cold Email Personalization at Scale (Sequencer and Reply).json
- sequencer-and-reply/AI-powered Outbound Cold Email Personalization at Scale(Sequencer and Reply).PNG

## Setup

1. Import both JSON files into separate n8n workflows.
2. Configure OpenAI, Gmail, and Google Sheets credentials.
3. Set the spreadsheet ID, sheet names, and column mappings.
4. Save and activate both workflows.

## Credentials required

- OpenAI API
- Gmail
- Google Sheets

![first email](./first-email/AI-powered Outbound Cold Email Personalization at Scale (First Email).PNG)
![sequencer](./sequencer-and-reply/AI-powered Outbound Cold Email Personalization at Scale(Sequencer and Reply).PNG)
