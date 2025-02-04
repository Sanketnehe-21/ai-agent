# AI Agent with Browser Automation

## 🚀 Overview
This AI Agent automates web searches and browsing tasks using the Python `browse` library. It interacts with a web UI to fetch website content without human intervention. The agent is configured using API keys to communicate with Large Language Models (LLMs), specifically **DeepSeek R1 (8B parameter model)** and **Gemini Flash** for enhanced processing capabilities.

🔗 **Repositories:**
- [Browser-Use Repository](https://github.com/browser-use/browser-use)
- [Web-UI Repository](https://github.com/browser-use/web-ui)

⚠️ **Confidentiality Notice:**
All files related to this project are confidential and should not be shared publicly.

---

## 📌 Features
- **Automated Web Browsing**: Performs searches and navigates websites autonomously.
- **AI-Powered Interactions**: Uses DeepSeek R1 and Gemini Flash for intelligent search.
- **Web UI Integration**: Easily control the agent via a UI.
- **API Key Configuration**: Secure LLM communication.

---

## 🔥 Quick Start
### 1️⃣ Install Dependencies
```sh
pip install browser-use
playwright install
```

### 2️⃣ Run the AI Agent
```python
from langchain_openai import ChatOpenAI
from browser_use import Agent
import asyncio
from dotenv import load_dotenv

load_dotenv()

async def main():
    agent = Agent(
        task="Go to a website, search for specific content, and return key information.",
        llm=ChatOpenAI(model="deepseek-r1-8b"),
    )
    result = await agent.run()
    print(result)

asyncio.run(main())
```

### 3️⃣ Configure API Keys
Add your API keys to the `.env` file:
```ini
OPENAI_API_KEY=your_openai_key
DEEPSEEK_API_KEY=your_deepseek_key
GEMINI_API_KEY=your_gemini_key
```

---

## 🖥️ Testing with Web UI
### Clone and Set Up Web UI
```sh
git clone https://github.com/browser-use/web-ui.git
cd web-ui
```

### Create a Virtual Environment (Recommended)
```sh
uv venv --python 3.11
source .venv/bin/activate  # macOS/Linux
.venv\Scripts\activate     # Windows (Command Prompt)
```

### Install Dependencies
```sh
uv pip install -r requirements.txt
playwright install
```

### Run Web UI
```sh
python webui.py --ip 127.0.0.1 --port 7788
```

Open **[http://127.0.0.1:7788](http://127.0.0.1:7788)** in your browser.

---

## 🐳 Docker Installation (Optional)
### Prerequisites
- Docker installed
- Docker Compose installed

### Steps
```sh
git clone https://github.com/browser-use/web-ui.git
cd web-ui
copy .env.example .env  # Windows
cp .env.example .env    # macOS/Linux
```
Edit `.env` and add API keys.

### Run with Docker
```sh
docker compose up --build  # Default (browser closes after tasks)
CHROME_PERSISTENT_SESSION=true docker compose up --build  # Keeps browser open
```

**Access Web Interface:** [http://localhost:7788](http://localhost:7788)

**View Browser in Real-Time:** [http://localhost:6080/vnc.html](http://localhost:6080/vnc.html)
(Default VNC password: `vncpassword`)

---

## 🌟 Additional Configuration
### Environment Variables
```ini
# LLM API Keys
OPENAI_API_KEY=your_openai_key
DEEPSEEK_API_KEY=your_deepseek_key
GEMINI_API_KEY=your_gemini_key

# Browser Settings
CHROME_PERSISTENT_SESSION=true
RESOLUTION=1920x1080x24

# VNC Settings
VNC_PASSWORD=your_vnc_password
```

### Run with Persistent Browser Mode
```sh
CHROME_PERSISTENT_SESSION=true docker compose up -d
```

---

## 🛠️ Troubleshooting
- **Playwright Errors**: Run `playwright install` again.
- **LLM Issues**: Verify API keys in `.env`.
- **Docker Issues**: Check if Docker is running.

---

### 🎯 Want More?
🔗 **[GitHub Repository](https://github.com/browser-use/browser-use)**  
💬 **[Join Discord](https://github.com/browser-use/browser-use)**  
📄 **[Read Documentation](https://github.com/browser-use/browser-use)**

