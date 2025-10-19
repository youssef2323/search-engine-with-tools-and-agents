# Chat with Search (Streamlit + LangChain + Groq)

## Overview
Chat with Search is a Streamlit app that answers user questions by intelligently choosing between web search, arXiv, and Wikipedia tools. A LangChain agent (Zero-Shot ReAct) coordinates tools, while a Groq LLM (llama-3.3-70b-versatile) generates the final response. Enter your Groq API key in the sidebar and start asking questions—no extra setup needed.

---

## Screenshots

### **Main Interface**
![Main Interface](screenshots/01-home.png)
*Caption: Streamlit app chat UI and sidebar.*

### **Example Output**
![Key Check](screenshots/02-key-check.png)
![Agent Steps](screenshots/03-callbacks.png)
![arXiv](screenshots/04-arxiv.png)
![Wikipedia](screenshots/05-wikipedia.png)
![Web Search](screenshots/06-search.png)
*Caption: Key validation, agent steps, and tool results.*

> Place images in a top-level `screenshots/` folder with simple names like `01-home.png`, `02-key-check.png`, etc.

---

## Features
- Natural-language Q&A with automatic tool selection (web search, arXiv, Wikipedia).
- Visible intermediate reasoning steps via Streamlit callback handler.
- Sidebar key entry with quick validation for `GROQ_API_KEY`.
- Simple chat history stored in `st.session_state`.

---

## Tools and Technologies
- **Streamlit** — UI and chat.
- **LangChain** — Agent orchestration & tool calling (Zero-Shot ReAct).
- **Groq** — `langchain_groq` with `llama-3.3-70b-versatile` (streaming).
- **DuckDuckGo** — Web search.
- **arXiv** — Scientific paper lookup.
- **Wikipedia** — Encyclopedic lookup.
- **python-dotenv** — Optional local environment variables.

---

## How It Works
1. User asks a question in the chat.
2. The LangChain agent decides which tool(s) to call (Search, arXiv, Wikipedia).
3. Tool outputs are returned to the agent.
4. The Groq LLM synthesizes a final, user-friendly answer.
5. Intermediate steps (thoughts/actions) are rendered in the UI for transparency.

---

## Configuration
- **Model name**: edit in `app.py` (default: `llama-3.3-70b-versatile`)
- **Agent iterations**: `max_iterations=3`
- **Tools**: enable/disable in `app.py` (DuckDuckGo, arXiv, Wikipedia)
- **API key**: paste `GROQ_API_KEY` in the sidebar (or load from `.env` if you prefer)

---

## Troubleshooting
- **Invalid key**: ensure it starts with `gsk_` and is long enough.
- **Search errors**: the app uses a safe wrapper; any failures are shown as friendly messages.

---

## License
MIT
