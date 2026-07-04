# Brownfield Application Workshop: Reverse Engineering & Improving Code with Agentic AI

A hands-on workshop teaching how to use AI coding tools to understand, audit, and improve existing codebases — the work that makes up 90% of real software engineering.

## What's Inside

- **[lab-reverse-engineering.md](lab-reverse-engineering.md)** — Hands-on lab: Reverse Engineering a Brownfield Application
- **[bob-Introduction.md](bob-Introduction.md)** — Introduction to IBM Bob IDE and Galaxium Travels

## Workshop Modules

1. **Understanding the Codebase** — Reverse-engineer architecture with AI in minutes
2. **Finding Problems** — Security audits, code quality, and test coverage analysis
3. **AI-Assisted Refactoring** — Live collaboration loop: plan, implement, test, review
4. **Discussion & Wrap-Up** — Reflect on AI-assisted development and its implications

## Primary Workshop Repo

The workshop uses [IBM/galaxium-travels](https://github.com/IBM/galaxium-travels) — a full-stack interplanetary travel booking app (Python + React/TypeScript) with intentional architectural challenges and pre-planted issues.

---

## Environment Setup

### Step 1: Install IBM Bob IDE

1. Visit [https://bob.ibm.com/docs](https://bob.ibm.com/docs)
2. Navigate to **IDE > Getting Started > Install**
3. Download and install Bob for your operating system (macOS, Windows, or Linux)
4. Launch Bob IDE and complete the initial setup

> Refer to the [Bob installation guide](https://bob.ibm.com/docs/ide/getting-started/install) for detailed platform-specific instructions.

### Step 2: Clone the Galaxium Travels Repository

```bash
git clone -b bob-learning-path-branch https://github.com/IBM/galaxium-travels
```

### Step 3: Open the Project in Bob IDE

1. Open Bob IDE
2. Select **File > Open Folder**
3. Navigate to and select the cloned `galaxium-travels` directory
4. Allow Bob to index the project (this may take a moment on first open)

### Step 4: Verify Setup

Once the project is loaded in Bob, confirm the following:

- The file explorer shows the project structure (frontend/, backend/, etc.)
- Bob's AI assistant is available in the sidebar or command palette
- The terminal within Bob can run commands in the project directory

---

## Prerequisites

- Basic programming knowledge (any language)
- Familiarity with Git (clone, branch, status)
- IBM Bob IDE installed ([bob.ibm.com/docs](https://bob.ibm.com/docs))
- Internet connection for AI features


## Resources

- [IBM Bob Documentation](https://bob.ibm.com/docs)
- [IBM Galaxium Travels Repository](https://github.com/IBM/galaxium-travels)
- [Bob Quickstart Tutorial](https://bob.ibm.com/docs/ide/getting-started/quickstart)
