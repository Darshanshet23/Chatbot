# 🤖 LangGraph Chatbot (Gemini + Meta-Llama + Tools)

A smart, multi-threaded **AI chatbot** built with **LangGraph**, **Streamlit**, and **SQLite checkpointing**, powered by **two LLMs** — Google **Gemini** and **Meta-Llama (Hugging Face)**.

---

## 🚀 Key Features

- 🧠 Uses **Gemini** (via LangChain Google GenAI) and **Meta-Llama** (via Hugging Face)  
- 🛠️ Integrated Tools: Calculator, Stock Price Fetcher, and Web Search  
- 💬 Real-time streaming responses  
- 💾 Persistent multi-threaded memory using SQLite  
- 🧱 Modular backend with LangGraph nodes and tool bindings  

---

## ⚙️ Setup Instructions

### 1️⃣ Clone and Install
```bash
git clone https://github.com/<your-username>/LangGraph-Chatbot.git
cd LangGraph-Chatbot
pip install -r requirements.txt
```

### 2️⃣ Environment Variables
Create a `.env` file:
```bash
GOOGLE_API_KEY=your_gemini_api_key_here
```

### 3️⃣ Run the Chatbot
```bash
streamlit run frontend.py
```

---

## 🧩 Tools Included

| Tool | Description |
|------|-------------|
| 🔢 Calculator | Perform add, sub, mul, div |
| 📈 Stock Price | Fetches real-time stock data |
| 🌐 Web Search | Uses DuckDuckGo for queries |

---

## 🧠 Architecture Overview

```
User → Streamlit UI → LangGraph → [Gemini / Meta-Llama]
                              ↓
                    ├── Calculator Tool
                    ├── Stock Price Tool
                    └── Search Tool
                              ↓
                     SQLite (Conversation Memory)
```

---

## 🧑‍💻 Author

**Darshan Shet**  
AI/ML Developer | LangChain | LLMs | Full-Stack AI Systems  
