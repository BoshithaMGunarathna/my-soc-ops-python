# 🎲 Soc Ops

> **Social Bingo for in-person mixers** — Find people who match the prompts and get 5 in a row!

[![Python 3.13](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![HTMX](https://img.shields.io/badge/HTMX-powered-3D72D7?logo=html5&logoColor=white)](https://htmx.org/)
[![uv](https://img.shields.io/badge/uv-package%20manager-DE5FE9)](https://docs.astral.sh/uv/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Soc Ops is a lightweight **Social Bingo** web app that turns any in-person mixer into a fun icebreaker. It is also the hands-on project for the **VS Code GitHub Copilot Agent Lab** — a workshop where you build real features using Copilot's Agent Mode, custom agents, and test-driven workflows.

---

## ✨ Features

- 🃏 **Randomised 5×5 bingo board** — fresh prompts every game
- 🆓 **Fixed FREE SPACE** in the centre
- ✅ **Instant win detection** — rows, columns, and diagonals
- 🔄 **Reset & play again** with a single click
- ⚡ **Zero-reload UI** powered by HTMX
- 🍪 **Session-based** — each player gets their own board

---

## 🚀 Quick Start

**Prerequisites:** Python 3.13+ and [uv](https://docs.astral.sh/uv/getting-started/installation/)

```bash
# 1. Clone the repo (or use this as a template)
git clone https://github.com/BoshithaMGunarathna/my-soc-ops-python.git
cd my-soc-ops-python

# 2. Install dependencies
uv sync

# 3. Run the app
uv run soc-ops
```

Open **http://localhost:8000** in your browser — that's it! 🎉

> 💡 **Tip:** Use the [DevContainer](.devcontainer) for a fully pre-configured environment in VS Code or GitHub Codespaces.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | [FastAPI](https://fastapi.tiangolo.com/) + Python 3.13 |
| **Templating** | [Jinja2](https://jinja.palletsprojects.com/) |
| **Frontend** | [HTMX](https://htmx.org/) (no JS framework required) |
| **Package manager** | [uv](https://docs.astral.sh/uv/) |
| **Linting / formatting** | [Ruff](https://docs.astral.sh/ruff/) |
| **Testing** | [pytest](https://pytest.org/) + [httpx](https://www.python-httpx.org/) |

---

## 📚 Workshop Lab Guide

This repo doubles as a **~1-hour Copilot Agent lab**. Work through the parts below to transform the app using VS Code's Agent Mode.

| Part | Title | Time |
|------|-------|------|
| [**00**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview) | Overview & Checklist | — |
| [**01**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup) | Setup & Context Engineering | 15 min |
| [**02**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design) | Design-First Frontend | 15 min |
| [**03**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master) | Custom Quiz Master | 10 min |
| [**04**](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent) | Multi-Agent Development | 20 min |

> 📝 Offline? All guides are available in the [`workshop/`](workshop/) folder.

---

## 🧪 Development

```bash
uv sync                  # install / sync deps
uv run ruff check .      # lint
uv run pytest            # run tests
```

---

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and follow the [Code of Conduct](CODE_OF_CONDUCT.md).

---

## 📄 License

[MIT](LICENSE) © BoshithaMGunarathna
