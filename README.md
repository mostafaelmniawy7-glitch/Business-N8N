## AI Business Chatbot

Production-ready AI chatbot for businesses (restaurants, pharmacies, clinics, stores). Built with n8n + Supabase + OpenAI.

## Features

- AI Agent with tool calling
- RAG using Supabase Vector Store
- Multi-tenant (one workflow, many businesses)
- Order creation and tracking
- Human handoff support
- Conversation memory per session

## Tech Stack

- n8n — Workflow automation
- Supabase — PostgreSQL + pgvector
- OpenAI — GPT-4o-mini + text-embedding-3-small

## Screenshots

### Main Workflow
![Workflow](screenshots/workflow.png)

### Supabase Database
![Supabase](screenshots/supabase.png)

## How It Works

1. User sends message via Webhook
2. AI Agent classifies intent (question / order / handoff)
3. Agent uses tools to answer or create order
4. Data saved to Supabase
5. Reply sent back to user

## API

POST /webhook/chatbot/{business_id}
Content-Type: application/json

{
  "message": "How much is the koshary?",
  "session_id": "user_123"
}

## Setup

1. Import `workflow.json` in n8n
2. Run `schema.sql` in Supabase
3. Add credentials (OpenAI, Supabase)
4. Add business data to `bot_businesses` and `bot_documents`
5. Activate the workflow

## Use Cases

- Restaurant orders and inquiries
- Pharmacy product information
- Clinic appointments
- Retail customer support

