# Demo Scripts for Brownfield Workshop

## Pre-Demo Setup

```bash
git clone https://github.com/IBM/galaxium-travels.git
cd galaxium-travels
docker compose up -d
```

---

## Demo 1: The "Cold Start" — Understanding a Codebase in 5 Minutes

### Narrative
> "Imagine you just joined a company. Day one. You're handed this repo. No onboarding doc. 
> Let's see how fast AI can get us productive."

### Commands (run inside Claude Code)

```
# Step 1: High-level architecture
> What is this project? Explain the architecture, services, and how they communicate. 
  Include the tech stack for each service.

# Step 2: Data model
> Show me the database schema. What are the main entities and their relationships?

# Step 3: API surface
> List all API endpoints in the backend. Group them by resource/domain.

# Step 4: Entry points & flows
> Trace the complete flow of a user booking a flight — from frontend click to database write. 
  Include all service-to-service calls.

# Step 5: Generate missing docs
> Generate an architecture diagram in Mermaid syntax for this project.
```

### What to highlight for audience:
- Speed of understanding (minutes vs days)
- AI correctly identifying inter-service communication patterns
- Generated documentation quality vs manual effort

---

## Demo 2: The "10-Minute Security Audit"

### Narrative
> "Before we add features, let's see what's wrong. A security audit that would take 
> a human reviewer hours — let's do it in minutes."

### Commands

```
# Full security scan
> Perform a security audit of this codebase. Focus on:
  1. Input validation issues
  2. Authentication/authorization gaps  
  3. SQL injection risks
  4. Information disclosure
  5. Error handling that leaks internals
  Report each finding with: severity, file:line, explanation, and fix.

# Specific deep dive
> The backend returns HTTP 200 for some error cases. Find all instances where errors 
  are masked as successful responses. Explain why this is a security/reliability concern.

# Dependency check
> Check all dependency files (requirements.txt, package.json, pom.xml) for known 
  vulnerable versions. Suggest upgrades.
```

### What to highlight:
- AI finding real architectural issues (HTTP 200 masking errors)
- Structured output with severity ratings
- Actionable fixes, not just complaints

---

## Demo 3: The "Live Refactoring" — Fix an Anti-Pattern

### Narrative
> "Now let's fix something. The repo has inconsistent error handling — some services 
> return union types, some throw exceptions. Let's standardize it."

### Commands

```
# Identify the pattern
> Find all places in the Python backend where functions return union types 
  (e.g., Result | Error) instead of raising exceptions. List each function 
  and explain the inconsistency.

# Plan the fix
> Propose a refactoring plan to standardize error handling in the backend. 
  Should we use exceptions or result types? Consider:
  - Consistency with FastAPI conventions
  - Impact on existing callers
  - Test implications

# Execute the fix (pick one function to demo live)
> Refactor the booking creation flow to use proper exception handling instead of 
  union return types. Update the route handler, service layer, and tests.

# Verify
> Run the tests to make sure our refactoring didn't break anything.
```

### What to highlight:
- AI understands architectural patterns, not just syntax
- It considers downstream impact before changing code
- Tests as safety net during refactoring

---

## Demo 4: The "Feature Sprint" — Implement from Issue

### Narrative
> "The repo has pre-planted feature requests. Let's pick one and implement it 
> end-to-end with AI assistance. This simulates real sprint work."

### Commands

```
# Pick Issue: Flight Status Chips (Tier-3, ~1-2 hours, compressed to 15 min demo)

# Step 1: Understand requirements
> Read the open issues for this repo. Find the "flight status chips" feature request.
  Explain what it needs and what files we'd need to touch.

# Step 2: Plan implementation
> Create an implementation plan for flight status chips. Include:
  - Backend changes (model, API)
  - Frontend changes (component, styling)  
  - Test additions

# Step 3: Implement backend
> Implement the backend changes for flight status. Add a status field to flights 
  with values: scheduled, boarding, departed, arrived, delayed, cancelled.

# Step 4: Implement frontend
> Create a FlightStatusChip React component that displays the flight status with 
  appropriate colors (green=on-time, yellow=boarding, red=delayed/cancelled). 
  Use it in the flight listing.

# Step 5: Write tests
> Write tests for the flight status feature — both backend unit tests and 
  frontend component tests.

# Step 6: Review our own work
> /code-review
```

### What to highlight:
- End-to-end feature implementation across multiple services
- AI writing tests (not just code)
- Using AI to review AI-generated code (meta!)

---

## Demo 5: The "Tool Comparison" — Same Task, Different Tools

### Narrative
> "Let's see how different AI tools approach the same problem. Each tool has 
> different strengths."

### Setup
Open the same file in different tools and ask each to improve it.

### Task: "Improve the booking validation logic"

**Claude Code (CLI):**
```
> Review the booking validation in the backend. Find edge cases that aren't handled 
  and add proper validation with meaningful error messages.
```

**What Claude Code does well:**
- Multi-file understanding (checks frontend validation too)
- Suggests architectural improvements
- Can execute and verify changes

**IBM Bob (if available):**
- Generates a spec first, then implements
- Enterprise-focused approach
- Good at maintaining consistency with existing patterns

**Copilot/Cursor (show briefly):**
- Great for inline suggestions
- Fast for single-file changes
- Less architectural awareness

---

## Demo 6: Quick "Wow Moment" (Use as opener or closer)

### The 60-Second Demo

```bash
cd galaxium-travels

# In Claude Code:
> In under 200 words, what are the 3 most impactful improvements you'd make to this 
  codebase if you had 1 day? Be specific — name files and line numbers.
```

Then immediately execute the top suggestion live.

---

## Troubleshooting During Demo

| Problem | Fix |
|---------|-----|
| Docker won't start | Use `docker compose down -v && docker compose up -d` |
| Claude Code rate limited | Switch to showing pre-recorded output |
| AI gives wrong answer | **Use this as a teaching moment** — show critical evaluation |
| Repo changed since prep | `git checkout` to a pinned commit |

---

## Tips for Presenters

1. **Pin a commit hash** — clone at a specific commit so the demo is reproducible
2. **Have pre-recorded fallbacks** — record terminal sessions with `asciinema` in case of network issues
3. **Embrace failures** — when AI gets something wrong, use it to teach critical thinking
4. **Let students try** — after each demo, give 10 min for hands-on
5. **Show the AGENTS.md file last** — it's the "answer key" that documents all the intentional traps
