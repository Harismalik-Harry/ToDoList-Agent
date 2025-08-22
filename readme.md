# ✅ ToDoList Agent with Memory & Trustcall

This project implements a **ToDoList Agent** using **LangGraph**, **Trustcall**, and **LangChain**. The agent dynamically manages user **to-do lists, profiles, and custom instructions**, making conversations more personalized and context-aware.

---

## ✨ Features

* 📝 **Smart ToDo Management**: Add, update, and track todos directly from chat.
* 📌 **Profile Memory**: Stores and updates user details.
* 🔄 **Dynamic Instructions**: Adjusts chatbot behavior based on user input.
* 🛠 **Trustcall Integration**: Extracts structured updates from conversations.
* 🧩 **LangGraph Flow**: Graph-based orchestration for managing state.
* 🤖 **LLM Support**: Works with OpenAI (`ChatOpenAI`) and Google Gemini (`ChatGoogleGenerativeAI`).

---

## 📂 Project Structure

```
.
├── main.py      # Core agent logic
├── utils.py               # Utility functions (Spy, tool info extraction)
├── schemas.py             # Pydantic schemas for Profile, ToDo, UpdateMemory
├── prompts.py             # System and tool instructions
├── configuration.py       # Configuration class for user/session handling
```

---

## ⚙️ How It Works

1. **Conversation Flow:**

   * User sends a message.
   * Agent checks stored profile, todos, and instructions.
   * Model generates response + tool calls if memory updates are needed.

2. **Memory Management:**

   * `update_profile`: Updates user profile.
   * `update_todos`: Updates ToDo list.
   * `update_instructions`: Updates custom instructions.

3. **Graph Execution:**

   * `task_mAIstro` → Generates responses.
   * `route_message` → Decides if updates are needed.
   * Memory update nodes (`update_*`) → Store changes.
   * Loop back to `task_mAIstro`.

---

## 🚀 Getting Started

### 1️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 2️⃣ Environment Variables

Create a `.env` file with your API keys:

```bash
GOOGLE_API_KEY=your_google_api_key
```

### 3️⃣ Run the Agent with LangGraph Studio

```bash
langgraph studio todolist_agent:graph
```

This will open the **LangGraph Studio UI**, allowing you to interact with the ToDoList Agent visually.

## 📦 Requirements

* **Python 3.9+**
* `langchain`
* `langgraph`
* `trustcall`
* `pydantic`
* `openai`
* `google-generativeai`

---


