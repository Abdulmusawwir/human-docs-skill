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
```
⚡ Quick Setup
Option 1: Copy-Paste to Any AI Agent
Copy the contents of SYSTEM_PROMPT.md and paste it as a custom instruction or system prompt into Cursor, Windsurf, OpenCode, Claude Code, or Aider.

Option 2: Add as a Project Skill
Save SYSTEM_PROMPT.md into your repository's workflow or rules folder (e.g., .cursor/rules/human-docs.md or .opencode/skills/human-docs.md).

🔥 Key Features
Emergency First: Includes 00-START-HERE.md so anyone can spin up the app offline with dummy local keys in under 5 minutes.

Zero Dead Links: The prompt strictly forbids hallucinated file paths—every path mentioned in the docs must actually exist in your codebase.

Automatic Cleanup: When features are deleted from your code, outdated guides are removed so documentation doesn't turn into bloated junk.

Inline Annotations: Write comments like // @human-doc: DO NOT change this delay in your code, and the agent automatically pulls them into the decision log.
