# AI Deep Research 

A deep research assistant that plans, searches the web, writes to a virtual filesystem, and renders each tool call as a live card in a workspace pane. Built with [CopilotKit](https://github.com/CopilotKit/CopilotKit), [Deep Agents](https://docs.copilotkit.ai/integrations/langgraph/deep-agents), and [Tavily](https://www.tavily.com/) on top of Next.js + LangGraph (Python).

The application is built with Next.js and TypeScript for the frontend, Python and FastAPI for the backend, and LangGraph with Deep Agents for managing the research workflow. CopilotKit and AG-UI provide the interactive interface between the user and the AI agent.

The research agent can understand a user's research question, create a research plan, perform web searches, analyze the collected information, and organize intermediate results using a virtual filesystem. The agent uses tools such as `write_todos`, `write_file`, `read_file`, and `research` to manage the research process.

## Key Features

- AI-powered research using Google Gemini
- Real-time web search using Tavily
- Multi-step research planning and analysis
- Interactive research workspace
- Live visualization of agent tool execution
- Virtual filesystem for managing research information
- Research planning using `write_todos`
- File management using `write_file` and `read_file`
- Web research using the `research` tool
- Next.js and React frontend
- Python FastAPI backend
- LangGraph and Deep Agents for agent orchestration
- CopilotKit and AG-UI for the interactive AI interface

## How It Works

The user enters a research question through the Next.js interface. CopilotKit sends the request to the Python backend, where the Deep Research Agent processes the task using LangGraph. The agent creates a research plan, performs web searches through Tavily, analyzes the retrieved information using Google Gemini, stores relevant research data in the virtual filesystem, and generates a final response for the user.

## Technology Stack

- **Frontend:** Next.js, React, TypeScript
- **Backend:** Python, FastAPI
- **AI Model:** Google Gemini
- **Agent Framework:** LangGraph, Deep Agents
- **AI Interface:** CopilotKit, AG-UI
- **Web Search:** Tavily
- **Development Tools:** VS Code, Git, GitHub

## Installation

### Prerequisites

Make sure the following are installed on your system:

- Node.js 18 or higher
- Python 3.12 or higher
- Git
- Google Gemini API Key
- Tavily API Key
- pip or uv

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/ai-deep-research-.git
cd ai-deep-research-
```

### 2. Install Frontend Dependencies

Install the required Node.js packages:

```bash
npm install
```

### 3. Setup the Python Environment

Move into the agent directory:

cd agent

Create a Python virtual environment:

python -m venv .venv

4. Activate the Virtual Environment

For Windows PowerShell:

.venv\Scripts\Activate.ps1

For Windows Command Prompt:

.venv\Scripts\activate

For macOS/Linux:

source .venv/bin/activate
5. Install Python Dependencies

Run:

pip install -e .

Return to the project root:

cd ..
API Configuration

# Create a .env file inside the agent directory:

ai-deep-research-agent/
│
└── agent/
    └── .env

# Add the following environment variables:

GEMINI_API_KEY=your_gemini_api_key
GEMINI_MODEL=gemini-3.5-flash
TAVILY_API_KEY=your_tavily_api_key


LANGGRAPH_DEPLOYMENT_URL=http://localhost:8123
SERVER_HOST=0.0.0.0
SERVER_PORT=8123
Get API Keys

Google Gemini API key:

https://aistudio.google.com/apikey

Tavily API key:

https://app.tavily.com/home


# Running the Project

The application requires two terminals: one for the Python backend and one for the Next.js frontend.

Terminal 1: Start the Backend

Open a terminal and navigate to the agent directory:

cd agent

Activate the virtual environment if it is not already active.

Then start the FastAPI backend:

python main.py

The backend will run at:

http://localhost:8123
Terminal 2: Start the Frontend

Open a second terminal and navigate to the project root:

cd ai-deep-research-agent

Start the Next.js development server:

npm run dev

The frontend will run at:

http://localhost:3000

Open http://localhost:3000 in your browser to use the application.

Example

Enter a research question such as:

What are the latest developments in artificial intelligence?

The agent will create a research plan, search the web using Tavily, analyze the retrieved information using Google Gemini, organize the research data, and generate a final response.

# Environment Variables
Variable	Required	Description
GEMINI_API_KEY	Yes	Google Gemini API key
GEMINI_MODEL	No	Gemini model used by the agent
TAVILY_API_KEY	Yes	Tavily web search API key
LANGGRAPH_DEPLOYMENT_URL	No	Backend URL
SERVER_HOST	No	Backend host
SERVER_PORT	No	Backend port

# Project Structure
ai-deep-research-agent/
│
├── agent/
│   ├── agent.py
│   ├── main.py
│   ├── tools.py
│   ├── pyproject.toml
│   ├── .env.example
│   └── .venv/
│
├── src/
│   ├── app/
│   ├── components/
│   └── ...
│
├── public/
├── .gitignore
├── package.json
├── package-lock.json
├── next.config.ts
└── README.md
Security

API keys must be stored in environment variables and should never be hard-coded into the source code.

Add the following to .gitignore:

.env
.env.*
!.env.example


.venv/
node_modules/
.next/
__pycache__/
*.pyc

If an API key is accidentally pushed to GitHub, revoke or rotate the key immediately.

# Future Enhancements
PDF upload and analysis
PDF summarization and question answering
Multiple document comparison
Automatic research citations
Research history
Research report generation
PDF and Word report export
CSV and Excel analysis
Charts and data visualization

# License
This project is intended for educational, learning, and portfolio purposes.
