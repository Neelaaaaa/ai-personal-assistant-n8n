# Personal AI Assistant (n8n Agent)

A conversational AI agent built using **n8n**, an automation/workflow tool. The agent can answer general questions, search the web, do calculations, and remembers context from earlier in the conversation.

## What it does

You chat with it like a regular assistant, and depending on what you ask, it automatically picks the right tool to answer:

- **General Q&A** — powered by Google Gemini (LLM)
- **Web search** — uses SerpApi to look up real-time information (e.g. weather, current events)
- **Calculations** — has a built-in calculator tool for math
- **Memory** — remembers previous messages in the same conversation, so you can ask follow-up questions naturally

## How it works

The workflow is built around an **AI Agent** node, which acts as the "brain." It decides which tool to use based on the question:

```
User message
     │
     ▼
 AI Agent (Google Gemini)
     │
     ├──► Simple Memory      (remembers chat history)
     ├──► Google Search (SerpApi)  (looks things up online)
     └──► Calculator         (does math)
```

For example:
- "What's the weather in Bangalore?" → Agent uses the **search tool**
- "What's 24 * 17?" → Agent uses the **calculator tool**
- "What did I just ask you?" → Agent uses **memory**

## Tools/Tech used

- **n8n** — visual workflow automation platform
- **Google Gemini API** — the language model powering the agent's reasoning
- **SerpApi** — for live web search results
- **n8n Simple Memory** — for conversational context

## Note

This was built using n8n's visual, low-code workflow builder rather than from scratch in code. It was a hands-on way to learn how AI agents work — how they decide which tool to use, hold memory, and chain steps together — concepts that carry over directly into building agents with code (e.g. using the Gemini/OpenAI SDKs directly in Python).

## How to use this workflow

1. Import `workflow.json` into your own n8n instance (Workflows → Import from File)
2. Add your own API keys for Google Gemini and SerpApi
3. Activate the workflow and start chatting via the built-in chat trigger
