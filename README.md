# 📈 Finance Agent with MCP + YFinance + Ollama LLM

This project is a lightweight financial assistant powered by MCP (Multi-Chain Processing), SmolAgents, and YFinance. It fetches stock prices, summarizes recent trends, and provides company background details using an LLM (Qwen 2.5 7B via Ollama) and modular tool execution.

---

## 🚀 Features

- 🔍 Fetch last month's stock closing prices using YFinance
- 🧠 Summarize stock data via LLM (Qwen 2.5 7B)
- 🏢 Retrieve business summary info for any publicly traded company
- 🤖 Interact with the assistant using natural language prompts (via MCP & ToolCallingAgent)

---

## 🧰 Tech Stack

- Python 🐍
- [YFinance](https://pypi.org/project/yfinance/)
- [MCP](https://github.com/multichain-processing)
- [SmolAgents](https://github.com/smol-ai/smol-agents)
- [Ollama](https://ollama.com/)
- [Langflow](https://github.com/logspace-ai/langflow)
- Colorama for CLI styling

---

## 🛠️ Installation & Setup

### 📦 Install Dependencies

Install required modules from the `requirements.txt` file:


---
pip install -r requirements.txt



## ⚙️ Part 1: Setting up the MCP Server and Inspector
1. Initialize a project using uv:
uv init

2. Create a virtual environment:
uv venv venv_name

3. Activate the virtual environment (adjust based on your OS):
source venv_name/bin/activate  # for macOS/Linux
venv_name\Scripts\activate     # for Windows

4. Run the MCP server (make sure server.py is present):
uv run mcp dev server.py

5. Open the Inspector using the URL printed in the terminal:
http://localhost:6274/?MCP_PROXY_AUTH_TOKEN=your_token_here

6. If there is a connection error, ensure:
You installed Node.js
You used the correct proxy session token in the Inspector URL
You changed the URL when clicking "Connect" to:

http://localhost:6274/?MCP_PROXY_AUTH_TOKEN=the_token_from_terminal


7. In the Inspector, click on any tool to:

Provide input

View structured output and logs


🤖 Part 2: Run Ollama Model Locally for Agent Use
1. Download & install the Ollama app.

2. Open a terminal and pull the model:
```ollama pull qwen2.5:7b```

3. Run the model:
ollama run qwen2.5:7b

3. Once the model is running, execute:
python agent.py


🧠 Part 3: Langflow Integration
There are two ways to integrate this system with Langflow:

Method A – Web App Interface
1.Install Langflow:
pip install langflow

2. Launch the Langflow app:
langflow run 

In the UI, drag and drop:

MCP Component

Ollama Component

Agent Component

Chat Input/Output

Make the following connections:

Ollama's output ➝ Language Model input

MCP's command: uv

Arguments: --directory path_to_server_folder run server.py

Interface: Select STDIO

Open the Playground tab and interact visually!

📝 Note: Ollama runs at http://localhost:11434 by default. Ensure Langflow points to this address.

---
