# Lab: Reverse Engineering a Brownfield Application

## Objective

In this lab, you will use an AI-powered IDE to reverse-engineer the **Galaxium Travels** application — a full-stack codebase you have never seen before. By the end of this lab, you will have a complete understanding of the application's architecture, data models, API surface, and service interactions — achieved in minutes rather than days.

This simulates a real-world scenario: joining a new team and needing to become productive in an unfamiliar codebase quickly.

---

## Prerequisites

Before starting this lab, ensure you have completed the environment setup from the [README](README.md):

- [ ] IBM Bob IDE installed and running
- [ ] Galaxium Travels repository cloned (`bob-learning-path-branch`)
- [ ] Project opened in Bob IDE

---

## Lab Structure

| Part | Focus Area | What You Will Produce |
|------|------------|----------------------|
| Part 1 | Project Overview & Architecture | High-level architecture summary |
| Part 2 | Data Model Discovery | Entity-relationship documentation |
| Part 3 | API Surface Mapping | Complete endpoint catalog |
| Part 4 | Flow Tracing | End-to-end booking flow diagram |
| Part 5 | Problem Identification | List of architectural concerns |
| Part 6 | Feature Implementation | Plan, code, tests for a new feature |

---

## Part 1: Project Overview & Architecture Discovery

**Context:** You have just opened a codebase for the first time. Your goal is to understand what this application does and how it is structured.

### Task 1.1 — Identify the Application Purpose

Using Bob's AI assistant, ask:

```
What is this project? Explain what this application does in 2-3 sentences.
```

**Record your findings:**
- Application name: _______________
- Primary purpose: _______________
- Target users: _______________

### Task 1.2 — Map the Architecture

Ask Bob:

```
Explain the architecture of this project. What are the main layers, 
what technologies does each layer use, and how do they communicate?
```

**Record your findings:**

| Layer | Technology | Responsibility |
|-------|-----------|----------------|
| Frontend | | |
| Backend | | |
| Database | | |

### Task 1.3 — Identify Entry Points

Ask Bob:

```
What are the main entry points to this application? 
How does the application start? List the key files that bootstrap each layer.
```

**Record your findings:**
- Frontend entry point: _______________
- Backend entry point: _______________
- Configuration files: _______________

---

## Part 2: Data Model Discovery

**Context:** Understanding the data model is foundational to understanding any application. You need to know what entities exist and how they relate.

### Task 2.1 — Discover Database Schema

Ask Bob:

```
Show me the database schema for this application. 
What are the main tables/models, their fields, and their data types?
```

### Task 2.2 — Map Entity Relationships

Ask Bob:

```
What are the relationships between the data models? 
Which entities reference each other? Describe the cardinality 
(one-to-one, one-to-many, many-to-many).
```

**Draw the relationships:**

```
Example format:
  User (1) ──── (many) Booking
  Flight (1) ──── (many) ???
```

Your diagram:
```
[Fill in the entity relationships you discover]
```

### Task 2.3 — Identify Seed Data

Ask Bob:

```
Is there any seed data or sample data in this project? 
What data is pre-loaded and where is it defined?
```

---

## Part 3: API Surface Mapping

**Context:** As a developer working on this codebase, you need to know what endpoints are available and what they do.

### Task 3.1 — List All Endpoints

Ask Bob:

```
List all REST API endpoints in the backend. For each endpoint, provide:
- HTTP method
- Path
- Brief description of what it does
Group them by domain/resource.
```

**Record your findings:**

| Method | Endpoint | Description |
|--------|----------|-------------|
| | | |
| | | |
| | | |

### Task 3.2 — Identify Authentication

Ask Bob:

```
How does authentication work in this application? 
What endpoints require authentication? How are users identified in requests?
```

**Record your findings:**
- Authentication mechanism: _______________
- Protected endpoints: _______________
- How credentials are passed: _______________

### Task 3.3 — Explore the MCP Interface

Ask Bob:

```
This application exposes an MCP interface in addition to REST. 
What is the MCP interface, what tools does it expose, and how 
does it differ from the REST API?
```

---

## Part 4: End-to-End Flow Tracing

**Context:** Understanding individual components is not enough — you need to understand how they work together to serve a user request.

### Task 4.1 — Trace the Booking Flow

Ask Bob:

```
Trace the complete flow of a user booking a flight — from the moment 
they click "Book" in the frontend to the final database write. 
Include every file touched, every function called, and every 
service-to-service communication.
```

**Document the flow as a sequence:**

```
Step 1: User clicks "Book" → [File/Component] →
Step 2: Frontend sends request → [Endpoint] →
Step 3: Backend processes → [Function/Service] →
Step 4: Database write → [Model/Table] →
Step 5: Response returns → ...
```

### Task 4.2 — Generate an Architecture Diagram

Ask Bob:

```
Generate a Mermaid diagram showing the complete architecture 
of this application, including all services, databases, 
and communication patterns.
```

**Paste the generated diagram here:**

```mermaid
[Paste diagram output]
```

### Task 4.3 — Identify Cross-Cutting Concerns

Ask Bob:

```
What cross-cutting concerns exist in this codebase? 
Look for: error handling patterns, logging, validation, 
and configuration management. Are these consistent across layers?
```

---

## Part 5: Problem Identification

**Context:** Now that you understand the codebase, use AI to identify areas that need improvement — the kind of analysis that demonstrates real engineering judgment.

### Task 5.1 — Architectural Concerns

Ask Bob:

```
What are the top 5 architectural concerns or anti-patterns in this codebase? 
For each, explain: what the issue is, where it occurs (file and line), 
why it is problematic, and what the recommended fix would be.
```

### Task 5.2 — Error Handling Audit

Ask Bob:

```
Analyze the error handling patterns in the backend. 
Are there places where errors are silently swallowed, 
where HTTP 200 is returned for error cases, or where 
error responses are inconsistent?
```

### Task 5.3 — Security Quick Scan

Ask Bob:

```
Perform a quick security review of this application. 
Focus on input validation, authentication gaps, 
and information disclosure risks. 
List findings with severity (High/Medium/Low).
```

---

## Part 6: Adding a New Feature to the Application

**Context:** Now that you fully understand the codebase, it is time to apply that knowledge. You will plan and implement a new feature — a **flight search filter** that allows users to search flights by destination. This exercise demonstrates the full AI-assisted development workflow: plan first, then implement.

### Task 6.1 — Define the Feature Requirements

Before writing any code, clearly define what you are building. Ask Bob:

```
I want to add a flight search/filter feature that lets users filter 
the flight list by destination. Help me define the requirements:
- What user interactions are needed?
- What backend changes are required?
- What frontend changes are required?
- Are there any edge cases to consider?
```

**Record the requirements:**
- User interaction: _______________
- Backend changes needed: _______________
- Frontend changes needed: _______________
- Edge cases: _______________

### Task 6.2 — Create an Implementation Plan

Ask Bob to generate a step-by-step plan before touching any code:

```
Create a detailed implementation plan for the flight search/filter feature. 
Break it into ordered steps with:
- Which files need to be modified or created
- What changes are needed in each file
- Dependencies between steps (what must be done first)
- How to test each step
```

**Review the plan critically:**
- Does the plan account for both frontend and backend?
- Are the steps in the correct dependency order?
- Is anything missing (error handling, edge cases, validation)?

**Write down any gaps you identify:**
```
[Note any issues or missing steps in the AI-generated plan]
```

### Task 6.3 — Implement the Backend Changes

Using the plan from Task 6.2, ask Bob to implement the backend first:

```
Implement the backend changes for the flight search feature based on our plan.
Add a query parameter to the flights endpoint that filters results by destination.
Ensure it handles: no matches, partial matches (case-insensitive), and empty filter 
(returns all flights).
```

**Verify the implementation:**
- [ ] New/modified endpoint accepts a search parameter
- [ ] Filtering logic is correct
- [ ] Empty search returns all results
- [ ] Search is case-insensitive

### Task 6.4 — Implement the Frontend Changes

Now ask Bob to implement the frontend:

```
Implement the frontend changes for the flight search feature.
Add a search input field above the flight list that filters displayed flights 
by destination as the user types. Use the backend endpoint we just created.
```

**Verify the implementation:**
- [ ] Search input is visible on the flights page
- [ ] Typing filters the flight list
- [ ] Clearing the input shows all flights again
- [ ] UI handles "no results" gracefully

### Task 6.5 — Write Tests

Ask Bob to add tests for the new feature:

```
Write tests for the flight search feature:
- Backend: test the filter endpoint with various inputs 
  (valid destination, no match, empty string, case sensitivity)
- Frontend: test that the search component renders, filters correctly, 
  and handles edge cases
```

### Task 6.6 — Review Your Own Implementation

Finally, ask Bob to review the code you just wrote together:

```
Review the flight search feature we just implemented. 
Check for: security issues, performance concerns, 
missing error handling, and consistency with the rest of the codebase.
```

**Record the review findings:**
- Issues found: _______________
- Improvements suggested: _______________
- Did you agree with the review? Why or why not?

---

## Deliverables

At the end of this lab, you should have:

1. A written architecture summary (from Parts 1-2)
2. A complete API endpoint catalog (from Part 3)
3. A documented end-to-end booking flow (from Part 4)
4. A Mermaid architecture diagram (from Task 4.2)
5. A prioritized list of issues/improvements (from Part 5)
6. A working new feature with implementation plan, code, and tests (from Part 6)

---

## Reflection Questions

After completing the lab, consider the following:

1. How long would this analysis have taken without AI assistance?
2. Did the AI get anything wrong? How did you verify its answers?
3. What questions did you need to ask differently to get useful answers?
4. What aspects of the codebase did AI struggle to explain clearly?
5. In Part 6, how useful was creating a plan before coding? Did the plan save you from mistakes?
6. Would you trust the AI-generated code to go to production without further review? Why or why not?
7. How would you use these techniques on your first day at a new job?

---

## Tips for Success

- **Be specific in your prompts** — vague questions get vague answers
- **Verify AI claims** — open the files it references and confirm the code matches its description
- **Iterate** — if an answer is unclear, ask a follow-up that narrows the scope
- **Think critically** — AI may hallucinate file names, function names, or relationships that do not exist
- **Document as you go** — do not wait until the end to write up your findings
