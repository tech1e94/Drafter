# 📝 Drafter AI Agent

An AI-powered document drafting assistant built using **LangChain, LangGraph, and Groq LLMs**. The agent helps users create, update, modify, and save text documents through natural language instructions.

Instead of manually editing files, users can interact with the AI agent conversationally, and it handles document updates using custom tools.

## 🚀 Features

- **AI-Powered Drafting:** Create and modify documents using natural language.
- **Document Updates:** Uses a custom `update` tool to replace the current document content.
- **Save Documents:** Saves the final document as a `.txt` file using the `save` tool.
- **Tool Calling:** Uses Groq LLM tool calling to determine when document operations are required.
- **State Management:** Maintains conversation history using LangGraph's message state.
- **Workflow Orchestration:** Uses a LangGraph StateGraph to manage the agent's execution flow.
- **Automatic Termination:** Ends the workflow when the document has been successfully saved.

## 🛠️ Tech Stack

- **Python** – Core programming language
- **LangChain** – LLM integration and tool calling
- **LangGraph** – Agent workflow orchestration and state management
- **Groq API** – LLM inference
- **Python-dotenv** – Environment variable management

## 📂 Project Structure

```text
Drafter-AI-Agent/
│
├── Drafter.py          # Main agent implementation
├── .env                # API credentials
├── requirements.txt    # Project dependencies
└── README.md           # Project documentation
```

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd Drafter-AI-Agent
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Alternatively:

```bash
pip install langchain langgraph langchain-groq python-dotenv
```

### 4. Configure Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

Replace the placeholder with your Groq API key.

## ▶️ Usage

Run the application:

```bash
python Drafter.py
```

The agent will start an interactive drafting session.

### Example Interaction

**User:**
```text
Create a document about Artificial Intelligence.
```

**AI:**
```text
Creates the initial document using the update tool.
```

**User:**
```text
Add a section about Machine Learning applications.
```

**AI:**
```text
Updates the document with the complete revised content.
```

**User:**
```text
Save the document as AI_Overview.
```

**AI:**
```text
Document has been successfully saved as 'AI_Overview.txt'.
```

The workflow terminates after successful saving.

## 🧠 How It Works

The project uses a graph-based agent architecture powered by LangGraph.

### Workflow

1. **User Input:** Accepts instructions through the terminal.
2. **Agent Processing:** The Groq-powered LLM interprets the user's request.
3. **Tool Selection:** The model decides whether to invoke the `update` or `save` tool.
4. **Tool Execution:** LangGraph's `ToolNode` executes the selected tool.
5. **State Management:** Conversation messages are maintained using `add_messages`.
6. **Conditional Routing:** The graph continues processing requests until the document is saved.
7. **Termination:** The workflow reaches `END` after successful saving.

### Available Tools

| Tool | Description |
|---|---|
| `update(content)` | Updates the current document with the complete revised content. |
| `save(filename)` | Saves the document as a `.txt` file. |

## 🔮 Future Improvements

- Support for PDF and DOCX document generation.
- Persistent document storage and retrieval.
- Multiple document management.
- Streaming responses.
- Improved error handling and validation.
- Web-based user interface.
- Support for more advanced document formatting.

## 📌 Key Learning Outcomes

- Building tool-calling AI agents using LangChain.
- Understanding graph-based workflows with LangGraph.
- Managing conversational state.
- Integrating Groq LLMs into Python applications.
- Implementing conditional routing and tool execution.

---

**Built with Python, LangChain, LangGraph, and Groq.**
