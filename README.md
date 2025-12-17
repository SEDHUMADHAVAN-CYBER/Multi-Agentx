# 🧠 Multi‑Agent RL Style System using LangGraph & Groq

This project demonstrates a multi‑agent system built using **LangGraph**, powered by the **Groq LLM API**, and enhanced with **RL‑style reward scoring**, **memory**, and optional **negotiation logic**.

## 🚀 Features
- Multi-agent architecture:
  - Planner Agent
  - Collaborator Agent
  - Competitor Agent
  - Negotiation Agent (optional)
  - Judge Agent (with reward scoring)
  - Memory Agent (optional)
- RL‑style numeric rewards (1–10)
- Self‑improving loop (training until reward threshold)
- Works on Google Colab
- Fast inference using Groq (Llama‑3.1‑8B‑Instant)

---

## 📦 Installation

```bash
pip install -q langgraph langchain-groq

🔑 Setup Groq API Key (in Google Colab)
Go to:

Runtime → Change runtime → Secrets
Add:

GROQ_API_KEY = your_api_key_here

🏗️ Agent Architecture
Planner
   ├── Collaborator →  
   │                   ──→ Negotiator → Judge → Memory
   └── Competitor  →

▶️ Running the Graph
state = {"user_input": "What is anesthesia?"}

final_state = multi_agent_graph.invoke(state)

print(final_state["final_output"])
print(final_state["reward"])
print(final_state["reward_score"])

 Optional: Self‑Improving RL Loop
train_until_good_answer("What is anesthesia?", threshold=8)

📁 Project Structure
/project
  ├── README.md
  ├── multi_agent.ipynb
  └── requirements.txt
