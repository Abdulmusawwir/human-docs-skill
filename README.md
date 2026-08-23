# 🛠️ Human Fallback (human-docs-skill)

> **What happens to your codebase if AI coding tools or agents suddenly stop working?**

Modern AI coding agents read code easily, but humans don't. When codebases rely heavily on AI context windows, traditional onboarding docs get neglected. If your AI tools go offline, taking over a complex project manually can turn into a nightmare.

**Human Fallback** is a single system prompt/skill that forces your AI agent to build and automatically maintain a `/human-docs/` folder in your repository. It acts as an emergency operational manual designed for a human engineer to run, extend, and debug the project completely offline.

---

## 🚀 How It Works

Whenever your AI agent writes or changes code, it automatically updates a set of human-friendly Markdown files in `/human-docs/`:

```text
/human-docs/
├── 00-START-HERE.md          # 5-minute offline setup & emergency start guide
├── 01-mental-model.md        # How the system works (with visual diagrams)
├── 02-architecture-map.md    # Folder structure, API dependencies, & databases
├── 03-recipes.md             # Step-by-step guides (e.g., "How to add a new API route")
├── 04-debugging-cheatsheet.md# Common error fixes & test commands
└── 05-decision-log.md        # Architectural rules you must NOT break
