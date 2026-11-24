# Client's Info and First Mail

When a new client submits their details via webhook, Groq drafts a customized first email, the lead is logged to Google Sheets, and the email is sent after a short wait.

## What it does

Receives client information through a webhook, uses a Groq language model to write a personalized first email, appends the client row to a tracking sheet, waits a few minutes, then sends the email to the client.

## How it works

1. Webhook - receives the client form submission (POST).
2. AI Agent - Groq (llama-3.3-70b-versatile) agent writes the customised first email (subject plus body).
3. Append row in sheet - logs the client info to Google Sheets.
4. Wait - pauses for a few minutes.
5. Send a message (Gmail) - sends the first email to the client's address.

## Nodes & services

Webhook, LangChain Agent (Groq llama-3.3-70b-versatile), Structured Output Parser, Google Sheets (append), Wait, Gmail.

## Files

- Client's Info and First Mail.json - n8n workflow export
- Client's_Info_and_First_Mail.PNG - canvas screenshot

## Setup

1. Import the JSON into n8n.
2. Configure Groq, Google Sheets, and Gmail credentials.
3. Set the webhook path, spreadsheet ID, and column names.
4. Save and activate.

## Credentials required

- Groq API
- Google Sheets
- Gmail

![canvas](./Client's_Info_and_First_Mail.PNG)
