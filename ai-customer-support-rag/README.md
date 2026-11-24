# AI Customer Support Agent (RAG)

Two-part RAG (Retrieval Augmented Generation) workflow: a support knowledge base is ingested into Pinecone, and incoming customer support emails are answered by retrieving from that knowledge base.

## What it does

Part 1 ingests frequently asked questions from a Google Drive document into a Pinecone vector store. Part 2 monitors a Gmail inbox, parses ticket emails, retrieves relevant answers from Pinecone, and either replies to the customer or escalates to the team on Slack.

## Part 1 - Data Ingestion

1. Manual Trigger - starts the ingestion run.
2. Google Drive - downloads the Repeatedly asked Queries document.
3. Default Data Loader - loads the document.
4. Recursive Character Text Splitter - splits text into chunks (500 chars, 55 char overlap).
5. Embeddings OpenAI - embeds chunks with OpenAI.
6. Pinecone Vector Store - inserts vectors into the Pinecone index.

## Part 2 - Query Responder

1. Gmail Trigger - polls for new customer query emails.
2. Parse Output (Code) - extracts subject, snippet, and sender from the raw email.
3. If escalated to team - decides whether the ticket needs human escalation.
4. Ticket Responding RAG Agent - Chain Retrieval QA agent (OpenAI chat model plus Pinecone Vector Store Retriever) that drafts an answer from the knowledge base.
5. Answer to Query - replies to the customer email thread via Gmail.
6. Inform Team (Slack) - flags escalated tickets to a Slack channel.

## Nodes & services

Manual Trigger, Google Drive, Default Data Loader, Recursive Character Text Splitter, OpenAI Embeddings, Pinecone Vector Store, Gmail Trigger, Code, IF, Chain Retrieval QA (OpenAI), Gmail, Slack.

## Files

- ingestion/AI customer support agent using RAG ( Ingestion ).json - part 1 export
- ingestion/AI customer support agent using RAG ( Ingestion ).PNG - part 1 screenshot
- query/AI customer support agent using RAG ( Query ).json - part 2 export
- query/AI customer support agent using RAG ( Query ).PNG - part 2 screenshot

## Setup

1. Import both JSON files into separate n8n workflows.
2. Configure OpenAI, Pinecone, Gmail, Google Drive, and Slack credentials.
3. Set the Pinecone index name, Google Drive file ID, and Gmail filter settings.
4. Save and activate both workflows.

## Credentials required

- OpenAI API
- Pinecone
- Gmail
- Google Drive
- Slack

![ingestion](./ingestion/AI customer support agent using RAG ( Ingestion).PNG)
![query](./query/AI customer support agent using RAG ( Query ).PNG)
