# Brownfield Application Workshop: Reverse Engineering & Improving Code with Agentic AI

## Workshop Overview

| Detail | Info |
|--------|------|
| **Audience** | Faculty & Students (CS/IT) |
| **Prerequisites** | Basic programming knowledge, Git basics |
| **Tools Needed** | IBM Bob IDE, Git |
| **Primary Repo** | [IBM/galaxium-travels](https://github.com/IBM/galaxium-travels) |

---

## Why Brownfield? (Opening Slide Talking Points)

- **90% of real engineering** is maintaining/improving existing code, not greenfield
- Companies hiring juniors want them to **navigate existing codebases** — this skill + AI tools = high leverage
- AI doesn't replace understanding — it **accelerates** it
- Reverse engineering with AI: generate docs, architecture diagrams, and explain unfamiliar codebases in **minutes instead of weeks**

---

## Primary Workshop Repo: IBM Galaxium Travels

### Why This Repo?

| Aspect | Details |
|--------|---------|
| **What** | Full-stack interplanetary travel booking app |
| **Stack** | Python (FastAPI) + React/TypeScript |
| **Size** | Manageable in a workshop setting |
| **Why it's great** | Purpose-built with intentional architectural challenges, pre-planted issues with difficulty tiers, mimics real enterprise patterns |

### Architecture

```
Frontend (React + TypeScript)
    |
    v [REST]
Backend API (Python FastAPI + SQLAlchemy)
    |
    v
SQLite (with seed data)
```

### Intentional "Brownfield" Challenges in This Repo

- Initialization order dependencies
- Inconsistent dependency injection patterns
- Union return types instead of proper exceptions
- HTTP 200 responses masking errors
- Double-patching requirements in tests
- Cross-service communication complexity

---

## Workshop Modules

### Module 1: Understanding the Codebase

**Goal:** Show how AI can reverse-engineer an unfamiliar codebase in minutes

**Activities:**
1. Clone the repo cold — no README reading
2. Use Bob to map architecture, entry points, data flows
3. Generate documentation that doesn't exist
4. Identify service boundaries and communication patterns

**Key Takeaway:** What used to take days/weeks of onboarding now takes minutes

---

### Module 2: Finding Problems

**Goal:** Use AI to systematically identify improvement areas

**Activities:**
1. Security audit (OWASP top 10)
2. Code quality review (duplication, dead code, anti-patterns)
3. Test coverage analysis
4. Performance bottleneck identification
5. Dependency vulnerability scanning

**Key Takeaway:** AI as a tireless code reviewer that catches what humans miss

---

### Module 3: AI-Assisted Refactoring

**Goal:** Live refactoring with AI — show the collaboration loop

**Activities:**
1. Pick an issue from the pre-planted tier-3 issues
2. Have Bob propose implementation plan
3. Implement with AI assistance
4. Write tests for the new code
5. Review the AI's output critically

**Key Takeaway:** AI accelerates implementation but humans must validate

---

### Module 4: Discussion & Wrap-Up

**Goal:** Reflect on AI-assisted development and its implications

**Discussion Points:**
- When did the AI get things right vs. wrong?
- How do you verify AI-generated code?
- What skills become more important in an AI-assisted workflow?
- How does this change the role of a developer?

---

## Hands-On Exercises (Pick 2-3)

### Exercise 1: Architecture Discovery (Beginner)
> Clone galaxium-travels. Without reading any documentation, use Bob to answer:
> 1. How many services are there?
> 2. How do they communicate?
> 3. What database(s) are used?
> 4. Draw the data flow for "booking a flight"

### Exercise 2: Security Audit (Intermediate)
> Use Bob to find at least 3 security concerns in the codebase.
> For each: explain the vulnerability, show the code, propose a fix.

### Exercise 3: Feature Implementation (Advanced)
> Pick one of the open issues (Tier-3 recommended):
> - Calendar export for bookings
> - Promo code system
> - Flight status chips
> Use Bob to implement it end-to-end including tests.

### Exercise 4: Cross-Service Bug Hunt (Advanced)
> The backend sometimes returns HTTP 200 for errors.
> Use Bob to find all instances, explain why this is problematic, and fix them.

---

## Assessment Rubric (For Faculty)

| Criteria | Points |
|----------|--------|
| Correct architecture understanding | 20 |
| Identified real issues (not false positives) | 25 |
| Quality of AI-assisted fix | 25 |
| Critical evaluation of AI output | 20 |
| Presentation/explanation | 10 |

---

## Setup Instructions (Pre-Workshop)

```bash
# 1. Install IBM Bob IDE
# Visit https://bob.ibm.com/docs/ide/getting-started/install
# Download and install for your platform

# 2. Clone the workshop repo
git clone -b bob-learning-path-branch https://github.com/IBM/galaxium-travels.git
cd galaxium-travels

# 3. Open in Bob IDE
# File > Open Folder > select galaxium-travels
```

---

## Resources & Links

- [IBM Galaxium Travels](https://github.com/IBM/galaxium-travels)
- [IBM Bob Documentation](https://bob.ibm.com/docs)
- [Bob Quickstart Tutorial](https://bob.ibm.com/docs/ide/getting-started/quickstart)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
