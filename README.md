<div align="center">

# 🎲 Soc Ops

### Social Bingo for In-Person Mixers

*Find people who match the prompts. Get 5 in a row. Break the ice.*

[![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![HTMX](https://img.shields.io/badge/HTMX-2.x-3D72D7?style=flat-square&logo=htmx&logoColor=white)](https://htmx.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![GitHub Copilot Lab](https://img.shields.io/badge/Copilot-Agent%20Lab-8957e5?style=flat-square&logo=github)](https://copilot-dev-days.github.io/agent-lab-python/docs/)

</div>

---

## ✨ What is Soc Ops?

**Soc Ops** is a lightweight, real-time **Social Bingo** web app built for in-person events, team mixers, and workshops. Each player gets a randomised 5×5 bingo card packed with conversation prompts. Mingle with the room, find people who match each square, and race to get **five in a row** — horizontally, vertically, or diagonally.

It's also the centrepiece of a **VS Code + GitHub Copilot Agent Lab** where you'll experience agentic AI-assisted development hands-on: context engineering, design-first frontend iteration, custom agents, and test-driven development.

---

## 🕹️ How to Play

| Step | Action |
|------|--------|
| **1** | Open the app on your device |
| **2** | Press **Start Game** to receive your unique card |
| **3** | Mingle and find someone who matches each square |
| **4** | Tap a square to mark it |
| **5** | Shout **BINGO!** when you get five in a row 🎉 |

> The centre square is a free space — you start with one match already!

---

## 🚀 Key Features

- 🃏 **Randomised boards** — every player gets a unique card drawn from a pool of 24 prompts  
- ⚡ **Live UI updates** — HTMX-powered interactions with zero full-page reloads  
- 🏆 **Win detection** — rows, columns, and both diagonals are checked automatically  
- 📱 **Mobile-friendly** — fully responsive layout works on any device  
- 🔄 **Reset & replay** — one tap to shuffle a brand-new card  

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | [FastAPI](https://fastapi.tiangolo.com/) + [Pydantic](https://docs.pydantic.dev/) |
| Frontend | [Jinja2](https://jinja.palletsprojects.com/) templates + [HTMX](https://htmx.org/) |
| Styling | Custom CSS utility classes (no external framework) |
| Runtime | Python 3.13 + [uv](https://docs.astral.sh/uv/) |
| Dev Tools | [Ruff](https://docs.astral.sh/ruff/) · [pytest](https://pytest.org/) |

---

## ⚡ Quick Start

### Prerequisites

- Python **3.13+**
- [uv](https://docs.astral.sh/uv/) package manager
- Git

### Run locally

```bash
# 1. Clone your fork (replace <you> with your GitHub username)
git clone https://github.com/<you>/my-soc-ops-python.git
cd my-soc-ops-python

# 2. Install dependencies
uv sync

# 3. Start the development server
uv run uvicorn app.main:app --reload
```

Open **http://localhost:8000** in your browser and you're ready to play!

### Dev commands

```bash
uv run ruff check .   # Lint
uv run pytest         # Test
```

> 💡 **Tip:** A [Dev Container](.devcontainer) is included — open in VS Code or GitHub Codespaces for a pre-configured environment with zero setup.

---

## 📚 Workshop Lab Guide

This repo doubles as a structured, ~1-hour workshop on **agentic AI development** with VS Code + GitHub Copilot. Work through the parts in order:

| Part | Title | Time | What you'll do |
|------|-------|------|----------------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | — | Prerequisites, goals, quick reference |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | 15 min | Configure Copilot instructions and teach the AI your codebase |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | 15 min | Let AI iterate on UI themes while you guide the vision |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | 10 min | Build a custom agent that generates creative bingo prompts |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | 20 min | Add new features using TDD agents (Red → Green → Refactor) |

> 📝 Offline copies of all lab guides are in the [`workshop/`](workshop/) folder.

Start here → **[Part 00: Overview & Checklist](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)**

---

## 🤝 Contributing

Contributions, issues and feature requests are welcome! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community standards.

---

## 📄 License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.
