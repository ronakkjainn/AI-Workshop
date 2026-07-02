# Brownfield Application Workshop: Reverse Engineering & Improving Code with Agentic AI

A hands-on workshop teaching how to use AI coding tools (Claude Code, IBM Bob, AWS Kiro, GitHub Copilot) to understand, audit, and improve existing codebases — the work that makes up 90% of real software engineering.

## What's Inside

- **[workshop-plan.md](workshop-plan.md)** — Full workshop structure with modules, exercises, and assessment rubric

## Workshop Modules

1. **Understanding the Codebase** — Reverse-engineer architecture with AI in minutes
2. **Finding Problems** — Security audits, code quality, and test coverage analysis
3. **AI-Assisted Refactoring** — Live collaboration loop: plan, implement, test, review
4. **Tool Comparison** — Strengths of different AI coding tools

## Primary Workshop Repo

The workshop uses [IBM/galaxium-travels](https://github.com/IBM/galaxium-travels) — a full-stack interplanetary travel booking app (Python FastAPI + Java Spring Boot + React/TypeScript) with intentional architectural challenges and pre-planted issues.

## Quick Start

```bash
# Install Claude Code
npm install -g @anthropic-ai/claude-code

# Install IBM Bob
# Visit https://bob.ibm.com and follow the installation instructions

# Clone the workshop target repo
git clone https://github.com/IBM/galaxium-travels.git
cd galaxium-travels

# Start services
docker compose up -d
```

## Prerequisites

- Basic programming knowledge
- Git basics
- Docker installed
- Claude Code CLI (or another AI coding tool)

## Who This Is For

Faculty and students in CS/IT programs looking to learn how AI tools accelerate real-world software engineering — not toy examples, but actual legacy codebase navigation, security auditing, and multi-service refactoring.
