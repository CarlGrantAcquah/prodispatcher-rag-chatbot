# ProDispatcher RAG Chatbot

A production RAG (Retrieval-Augmented Generation) chatbot 
built with n8n, Google Gemini, and Pinecone.

## Demo
[Watch the Loom demo]([your loom link here])

## Tech Stack
- n8n (workflow orchestration)
- Google Gemini gemini-embedding-2-preview (embeddings)
- Google Gemini 2.5 Flash (LLM)
- Pinecone (vector database, 3072 dimensions)
- Webhook API (real-time query interface)

## Architecture
Webhook → Extract Question → QA Chain → Format Response → Send Response
                                 ↑              ↑
                     Vector Store Retriever   Gemini Flash
                                 ↑
                     Pinecone Vector Store ← Gemini Embeddings

## How to Run
1. Import `n8n-workflow-INGESTION.json` into your n8n instance
2. Add your Pinecone and Google Gemini credentials
3. Create a Pinecone index named `prodispatcher-kb` with 3072 dimensions
4. Execute the ingestion workflow
5. Import `n8n-workflow-CHATBOT.json`
6. Activate the workflow
7. POST to the webhook URL with `{"question": "your question"}`

## Built by
Carl Grant-Acquah — AI Automation Specialist
linkedin.com/in/carl-grant-acquah
