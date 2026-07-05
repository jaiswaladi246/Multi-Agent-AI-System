# Multi-Agent AI Blog Writer using Google ADK

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Google ADK](https://img.shields.io/badge/Google-ADK-green)
![Gemini](https://img.shields.io/badge/Gemini-3.1%20Flash%20Lite-orange)
![License](https://img.shields.io/badge/License-MIT-blue)

A production-style **Multi-Agent AI Blog Writer** built using the **Google Agent Development Kit (ADK)**.

Instead of relying on a single AI agent, this project demonstrates how **multiple specialized AI agents** collaborate to generate high-quality technical blog posts through **planning, validation, and self-correction**.

The project follows a **Planning + Reflection** workflow where every stage is validated before moving to the next.

---

# 👨‍💻 Author

Created by **Aditya Jaiswal**

Founder of **DevOps Shack**, where we teach DevOps, Cloud, Kubernetes, DevSecOps, MLOps, and AI Engineering through practical, production-grade projects.

### 🌐 Connect with DevOps Shack

- 📺 YouTube: https://www.youtube.com/@devopsshack
- 📸 Instagram: https://www.instagram.com/devopsshack
- 💼 LinkedIn: https://www.linkedin.com/in/adityajaiswal7/

---

# 🚀 Features

- 🤖 Multi-Agent AI Architecture
- 🧠 Planning Agent
- ✍️ Blog Writing Agent
- ✅ Validation Agents
- 🔄 Self-Correcting Workflow
- 🔁 Automatic Retry Mechanism
- 📄 Markdown Blog Generation
- 📚 1200–1800 Word Articles
- 📰 Alternate Blog Titles
- 🐦 Tweet Hooks Generation
- ⚡ Built using Google ADK

---

# 🏗️ Architecture

```text
                    User
                      │
                      ▼
              ┌─────────────────┐
              │   Blogger Agent │
              │   (Root Agent)  │
              └─────────────────┘
                 │           │
                 │           │
                 ▼           ▼
      Planner Tool       Writer Tool
           │                  │
           ▼                  ▼
 ┌─────────────────┐  ┌─────────────────┐
 │ Robust Planner  │  │ Robust Writer   │
 │   (LoopAgent)   │  │   (LoopAgent)   │
 └─────────────────┘  └─────────────────┘
        │    ▲               │    ▲
        │    │               │    │
        ▼    │               ▼    │
 Blog Planner│         Blog Writer│
             │                   │
             ▼                   ▼
 Outline Checker        Blog Checker
```

---

# 📁 Project Structure

```text
bloggeragent/
│
├── agent.py
├── __init__.py
├── requirements.txt
├── .env
└── README.md
```

---

# 🛠️ Tech Stack

- Python
- Google ADK
- Gemini API
- python-dotenv

---

# 📋 Prerequisites

Before getting started, make sure you have:

- Python 3.10+
- pip
- Google AI Studio API Key
- Virtual Environment Support

---

# ⚙️ Installation

## 1. Clone the Repository

```bash
git clone https://github.com/jaiswaladi246/Multi-Agent-AI-System.git

cd bloggeragent
```

---

## 2. Create the Required Files

```bash
touch requirements.txt .env __init__.py agent.py
```

---

## 3. Configure Requirements

Open **requirements.txt**

```text
google-adk==2.2.0
python-dotenv
```

---

## 4. Create Virtual Environment

Ubuntu

```bash
sudo apt update
sudo apt install python3-venv -y
```

Create virtual environment

```bash
python3 -m venv .venv
```

Activate it

```bash
source .venv/bin/activate
```

---

## 5. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 6. Configure Gemini API

Create a `.env` file

```text
GOOGLE_API_KEY=your_api_key
```

Replace `your_api_key` with the API key generated from Google AI Studio.

---

# 🤖 Model Used

This project uses:

```text
gemini-3.1-flash-lite
```

The model is lightweight, fast, and suitable for building multi-agent applications with Google ADK. It also supports the Gemini API Free Tier, making it a great choice for learning and experimentation.

If you'd like to use a different Gemini model, simply update the `MODEL` environment variable or change the default value in `agent.py`.

Example:

```python
MODEL = os.getenv("MODEL", "gemini-3.1-flash-lite")
```

---

# 🔄 Multi-Agent Workflow

## Step 1 — User submits a topic

Example

```text
Explain Kubernetes Networking
```

The request first reaches the **Blogger** Root Agent.

---

## Step 2 — Planning Phase

The Planner Agent creates a structured outline.

Example

```text
Title

Introduction

Core Concepts

Architecture

Practical Examples

Best Practices

Conclusion
```

---

## Step 3 — Outline Validation

The Outline Validation Agent reviews the generated outline.

If incomplete

```text
retry
```

The Planner runs again.

Otherwise

```text
ok
```

The workflow proceeds.

---

## Step 4 — Blog Writing

The Blog Writer converts the outline into a detailed technical article.

Generated article contains

- H1 Title
- Introduction
- Multiple H2 Sections
- Practical Examples
- Code Snippets
- Best Practices
- Conclusion

---

## Step 5 — Blog Validation

A second validation agent reviews the complete article.

It checks

- Technical clarity
- Missing sections
- Introduction
- Conclusion
- Structure
- Overall quality

If required

```text
retry
```

The writing loop runs again.

---

## Step 6 — Final Response

The Blogger Root Agent returns

- Complete Blog
- Three Alternate Titles
- Two Tweet-Length Hooks

---

# 🤖 Agents Used

| Agent | Responsibility |
|--------|----------------|
| **Blogger** | Root agent that orchestrates the workflow |
| **Blog Planner** | Creates the blog outline |
| **Outline Validation Checker** | Reviews the outline |
| **Blog Writer** | Generates the complete article |
| **Blog Validation Checker** | Reviews the final article |

---

# 🎯 Why Multi-Agent Instead of One Agent?

A single AI agent has to think about planning, writing, reviewing, and correcting everything simultaneously.

This project separates those responsibilities into specialized agents.

Benefits include:

- Better blog quality
- Better planning
- Self-correction
- Easier debugging
- More reliable outputs
- Modular architecture
- Easier to extend

This design closely resembles how real production AI systems are built.

---

# ▶️ Running the Project

Activate the virtual environment

```bash
source .venv/bin/activate
```

Start the ADK Web Interface

```bash
adk web --host 0.0.0.0 --port 8000
```

---

# 🌐 Access the Web UI

Local Machine

```text
http://127.0.0.1:8000
```

EC2

```text
http://<YOUR_PUBLIC_IP>:8000
```

---

# 💬 Example Prompts

```
How to Build AI Agents using Planning Loops
```

```
Explain REST vs gRPC
```

```
Docker Best Practices
```

```
Python AsyncIO Complete Guide
```

```
Kubernetes Networking Explained
```

```
How GitOps Works
```

---

# 📚 Learning Outcomes

After completing this project, you'll understand

- Google ADK Fundamentals
- Multi-Agent AI Systems
- Planning Agents
- Validation Agents
- LoopAgents
- Agent Tools
- Workflow Orchestration
- Self-Correcting AI Pipelines

---

# 🚀 Future Improvements

- Retrieval-Augmented Generation (RAG)
- Internet Search Integration
- Memory Support
- PDF Export
- SEO Optimization
- Image Generation
- Human Approval Workflow
- Vector Database Integration

---

# ⭐ Support the Project

If you found this repository helpful, please consider

- ⭐ Star this repository
- 🍴 Fork it
- 🐛 Report Issues
- 💡 Suggest Improvements
- 📢 Share it with others

Every ⭐ helps the project reach more developers.

---

# 🚀 Learn More with DevOps Shack

If you're interested in learning through practical, production-grade projects, check out **DevOps Shack**.

We regularly publish content on

- 🤖 AI Agents
- ☁️ Cloud Computing
- ⚙️ DevOps
- 🔐 DevSecOps
- ☸️ Kubernetes
- 🐳 Docker
- 🚀 CI/CD
- 📈 MLOps

### Follow DevOps Shack

📺 YouTube  
https://www.youtube.com/@devopsshack

📸 Instagram  
https://www.instagram.com/devopsshack

💼 LinkedIn  
https://www.linkedin.com/company/devopsshack

https://www.linkedin.com/in/adityajaiswal7/

⭐ If this project helped you, don't forget to **Star the Repository!**

Happy Learning! 🚀

---

# 📄 License

This project is released for educational purposes and demonstrates how to build **Multi-Agent AI Systems** using the **Google Agent Development Kit (ADK)**.
