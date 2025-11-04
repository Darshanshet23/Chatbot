# 🤖 LangGraph Chatbot (with Gemini + Tools + Auto Chat Titles)

A fully functional **AI Chatbot** built using **LangGraph**, **Google Gemini (via LangChain)**, and **Streamlit** — featuring:
- Tool usage (Calculator, Stock Price, Web Search)
- Multi-threaded conversation memory using **SQLite Checkpointing**
- Real-time streaming responses
- Persistent conversation history

---

## 🚀 Features

✅ **Powered by Gemini (Google Generative AI)**  
✅ **Dynamic Tool Calling** – supports search, calculator, and stock lookup  
✅ **Persistent Multi-Threaded Memory** using SQLite  
✅ **Interactive UI** with Streamlit  
✅ **Live Response Streaming**

---

## 🧩 Project Structure

```
📂 LangGraph-Chatbot
├── backend.py          # LangGraph graph + tools + memory logic
├── frontend.py         # Streamlit interface
├── .env                # Contains your GOOGLE_API_KEY
├── chatbot.db          # SQLite checkpoint storage
└── README.md           # Project documentation
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/<your-username>/LangGraph-Chatbot.git
cd LangGraph-Chatbot
```

### 2️⃣ Create Virtual Environment
```bash
python -m venv venv
venv\Scripts\activate  # On Windows
source venv/bin/activate  # On Mac/Linux
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

If you don’t have a `requirements.txt` yet, create one:
```bash
langchain-google-genai
langchain-core
langchain-community
langgraph
streamlit
python-dotenv
requests
duckduckgo-search
```

---

## 🔑 Environment Variables

Create a `.env` file in the root directory:

```bash
GOOGLE_API_KEY=your_gemini_api_key_here
```

Get your free Gemini API key from:
👉 [https://aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey)

---

## 🧠 How It Works

### **1. LLM Setup**
Uses **Google Gemini (via LangChain)** for reasoning and title generation.

```python
llm = ChatGoogleGenerativeAI(
    model="gemini-2.0-flash",
    google_api_key=google_api_key,
    temperature=0.3
)
```

### **2. Tools**
Built-in tools include:
- 🔢 Calculator (`add`, `sub`, `mul`, `div`)
- 📈 Stock Price Fetcher (via AlphaVantage)
- 🌐 Web Search (DuckDuckGo)

### **3. Memory (SQLite Checkpointer)**
Each conversation (thread) is stored persistently in `chatbot.db` using `SqliteSaver`.

### **4. Auto Chat Titles**
When a user starts a new chat, Gemini automatically generates a short, meaningful title like:
> “Stock Price Query” or “Python Debug Help”

These titles are stored in a `chat_titles` table and displayed in the Streamlit sidebar.

---

## 💬 Running the App

Run your chatbot locally using Streamlit:

```bash
streamlit run frontend.py
```

Then open the local URL (usually [http://localhost:8501](http://localhost:8501)) in your browser.

---

## 🖥️ UI Overview

**Sidebar:**
- Start a **New Chat**
- See all **past chat titles**
- Click to **resume** any old conversation

**Main Chat Area:**
- Real-time streamed messages
- Tool usage feedback (shows when a tool runs)
- Persistent history per thread

---

## 🧱 Database Structure

**Tables:**
- `checkpoints` → stores serialized LangGraph conversation states  
- `chat_titles` → stores `thread_id` → `title` mappings  

---

## 🧩 Example Use Cases

| Task | Example Prompt | Tool Used |
|------|----------------|-----------|
| Web Search | “Who is the CEO of Tesla?” | DuckDuckGo |
| Stock Info | “Get stock price of AAPL” | Stock Tool |
| Calculator | “Multiply 45 and 7” | Calculator |
| General Chat | “Explain LangGraph in simple terms” | LLM |

---

## 🧠 Architecture Diagram (Simplified)

```
User → Streamlit UI → LangGraph → Gemini LLM
                             ↓
                    ├── Calculator Tool
                    ├── Search Tool
                    └── Stock Tool
                             ↓
                 SQLite Checkpointer (Memory)
```

---

## 🧾 Example Chat Title Flow

| User's First Message | Auto-Generated Title |
|----------------------|----------------------|
| “Check Tesla stock price” | “Stock Price Query” |
| “Add 25 and 19” | “Calculator Chat” |
| “Explain LangGraph basics” | “LangGraph Overview” |

---

## ⚡ Future Improvements

- 🪄 Add dynamic renaming after 3–4 messages (context-aware titles)  
- 🗂️ Add chat export / delete feature  
- 🧠 Integrate memory summarization for long chats  
- 🌍 Add more tools (weather, news, etc.)  

---

## 🧑‍💻 Author

**Darshan Shet**  
AI/ML Developer | LangChain | Generative AI | Full-Stack AI Systems  

---

## 🪪 License
This project is open-source and available under the **MIT License**.

---

### ⭐ If you found this helpful, give it a star on GitHub! ⭐
