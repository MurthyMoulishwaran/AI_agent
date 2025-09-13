# Student Data Retrieval Agent — n8n + Local LLM

## 📌 Overview  
This project demonstrates how to build a **data retrieval agent** using **n8n** and a **local LLM**.  
The workflow accepts **natural-language queries**, converts them into **safe, parameterized SQL** using a locally hosted LLM, executes the queries against a **student database**, and returns structured results automatically.

---

## 🔹 Features  
- 🧑‍💻 **Natural Language to SQL**: Users can query in plain English.  
- 🤖 **Local LLM Integration**: LLM runs on the developer’s machine, exposed via an **OpenAI-compatible API**.  
- 🔐 **Privacy-First**: No external API calls, all processing happens locally.  
- 🛡️ **Safe Queries**: SQL generation is validated with column whitelists, parameterization, and query limits.  
- ⚡ **Automated Retrieval**: Returns filtered student information in real-time.  
- 🔄 **Extensible**: Workflow can be extended to other datasets or UI integrations.

---

## 🔹 Tech Stack  
- **n8n** – Workflow automation  
- **Local LLM** – GPT4All / LocalAI / LLaMA-based model (OpenAI API-compatible)  
- **SQL Database** – SQLite / MySQL / PostgreSQL  
- **Nodes Used** – Webhook, Function, HTTP Request (LLM), SQL Node, Response Node  

---

## 🔹 Architecture  

**Workflow Steps:**  
1. **Trigger Node** – Accepts natural-language query (manual input, webhook, or UI).  
2. **Function Node** – Prepares schema + formats query prompt.  
3. **Local LLM** – Converts NL query into a parameterized SQL statement.  
4. **Validation Layer** – Ensures only safe, whitelisted SQL commands pass through.  
5. **SQL Node** – Executes validated SQL query on student database.  
6. **Output Node** – Returns structured results (JSON, CSV, or table).  

---

