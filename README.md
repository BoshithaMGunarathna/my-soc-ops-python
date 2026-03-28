<div align="center">

# 💻 Tech Life Bingo

### *Developer Edition — Code, Culture & Chaos*

**An interactive bingo game celebrating coding habits, IDE wars, and developer culture**

[![Python 3.13+](https://img.shields.io/badge/python-3.13+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-green.svg)](https://fastapi.tiangolo.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

[Quick Start](#-quick-start) • [Features](#-features) • [Lab Guide](#-lab-guide) • [Tech Stack](#️-tech-stack)

</div>

---

## 🎮 What is Tech Life Bingo?

Tech Life Bingo is an interactive **developer-themed bingo game** built for tech events, team standups, hackathons, and engineering meetups. Each square on the 5×5 board features a relatable coding habit, IDE preference, or developer culture moment. Find fellow devs who match each square, mark your board, and get 5 in a row to win!

Perfect for:
- 🖥️ **Engineering Teams** - Onboarding, retrospectives, and team socials
- 🎓 **Hackathons & Bootcamps** - Icebreakers for devs of all levels
- 🎉 **Tech Meetups & Conferences** - Networking with a nerdy twist
- 🤝 **Developer Communities** - Celebrating shared coding quirks

---

## ✨ Features

- 🎲 **Dynamic Question Generation** - Powered by an AI quiz master agent
- 📱 **Mobile-First Design** - Works seamlessly on any device
- ⚡ **Real-Time Interaction** - Built with HTMX for smooth, app-like experience
- 🎨 **Beautiful UI** - Clean, modern interface with thoughtful animations
- 🔒 **Privacy-Focused** - No database, all games stored in memory
- 🚀 **Zero Dependencies** - Runs locally with minimal setup

---

## 🚀 Quick Start

### Prerequisites
- Python 3.13 or higher
- [uv](https://docs.astral.sh/uv/) package manager

### Installation

```bash
# Clone the repository
git clone https://github.com/BoshithaMGunarathna/my-soc-ops-python.git
cd my-soc-ops-python

# Install dependencies
uv sync

# Run the application
uv run soc-ops
```

Visit **http://localhost:8000** and start playing! 🎉

### Development Mode

```bash
# Run tests
uv run pytest

# Lint code
uv run ruff check .

# Watch for changes (development)
uvicorn app.main:app --reload
```

---

## 🎯 How to Play

1. **Start a New Game** - Generate a fresh 5×5 bingo board with developer prompts
2. **Read the Squares** - Each square describes a coding habit or dev culture moment
3. **Find Your Fellow Devs** - Talk to others and find someone who matches each square
4. **Mark Your Board** - Click squares to track your progress
5. **Get 5 in a Row** - Complete a line (horizontal, vertical, or diagonal) to win!

> 💡 **Pro Tip:** The center square is a free space — it's already shipped!

---

## 📚 Lab Guide

This project is part of an interactive agent development workshop. Learn how to build AI-powered applications using GitHub Copilot and modern development practices:

| Part | Title | Focus |
|:----:|-------|-------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | Prerequisites and setup |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | Project structure and configuration |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | Building beautiful UIs with Copilot |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | Creating custom AI agents |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | Orchestrating multiple agents |

> 📝 **Offline Access:** All lab guides are available in the [`workshop/`](workshop/) folder

---

## 🛠️ Tech Stack

<table>
<tr>
<td width="50%">

**Backend**
- [FastAPI](https://fastapi.tiangolo.com/) - Modern Python web framework
- [Jinja2](https://jinja.palletsprojects.com/) - Powerful templating engine
- [Uvicorn](https://www.uvicorn.org/) - Lightning-fast ASGI server

</td>
<td width="50%">

**Frontend**
- [HTMX](https://htmx.org/) - High-power tools for HTML
- Custom CSS - Utility-first styling
- Progressive Enhancement - Works without JavaScript

</td>
</tr>
</table>

---

## 📖 Project Structure

```
my-soc-ops-python/
├── app/
│   ├── main.py              # FastAPI application & routes
│   ├── game_logic.py        # Pure game logic (board, validation)
│   ├── game_service.py      # Session & state management
│   ├── models.py            # Pydantic models
│   ├── data.py              # Question bank
│   ├── templates/           # Jinja2 templates
│   └── static/              # CSS and assets
├── tests/                   # Test suite
├── workshop/                # Lab guides
└── pyproject.toml           # Project configuration
```

---

## 🤝 Contributing

Contributions are welcome! Please check out our [Contributing Guidelines](CONTRIBUTING.md) and [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

Built as part of the GitHub Copilot Developer Days workshop, demonstrating modern AI-assisted development practices.

---

<div align="center">

**[⬆ Back to Top](#-soc-ops)**

Made with ❤️ and GitHub Copilot

</div>
