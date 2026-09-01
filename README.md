# AI Project Template

A lightweight, tool-agnostic project memory system for AI-assisted work.

Designed so Claude Code, Codex, Cursor, and other AI agents can understand the project state and continue work across sessions without relying on chat history.

## Structure

```text
project/
├── CLAUDE.md
├── AGENTS.md
└── docs/
    ├── PROJECT.md
    ├── DECISIONS.md
    ├── PROGRESS.md
    └── TODO.md
```

## How It Works

The files in `docs/` act as persistent project memory:

- `PROJECT.md` — what the project is and what it should achieve
- `DECISIONS.md` — important confirmed decisions and their reasoning
- `PROGRESS.md` — the current state of the project and the recommended next action
- `TODO.md` — prioritized remaining work

`CLAUDE.md` and `AGENTS.md` instruct AI tools to read and maintain this shared memory.

## Start a New Project

1. Copy this repository into your new project.
2. Fill in `docs/PROJECT.md`.
3. Ask your AI assistant to read the project memory before starting.
4. Work normally.
5. Before ending a meaningful session, let the AI update `PROGRESS.md`, `TODO.md`, and `DECISIONS.md`.

Example startup prompt:

> Read the project memory files, summarize the current state, and continue from the Next Action.

Example closing prompt:

> Before we stop, update the project memory with what was completed, current work, important decisions, blockers, remaining tasks, and the recommended next action.

## Optional Files

Add these only when the project needs them:

- `docs/ARCHITECTURE.md` — software/system architecture
- `docs/DESIGN_SYSTEM.md` — UI/UX and design-system rules
- `docs/API.md` — API contracts and integration notes
- `docs/RESEARCH.md` — research findings and references

## Principle

Conversation history is temporary. Project memory belongs to the project.

The goal is to make it possible for another AI agent — or your future self — to resume the project with minimal context loss.