# 🚀 Project README

This repository is designed to support an **AI-assisted development workflow**. The documentation in `/docs` helps you define the project clearly, keep the AI aligned, and reduce confusion during implementation.

---

## 📝 Setup Instructions

1. Copy the entire `/docs` folder into the root of your project.
2. Ensure the folder contains:
   - `overview.md`
   - `architecture.md`
   - `roadmap.md`
   - `instructions.md`
   - `guides/documentation-guide.md`
3. If you are using AI to write or update documentation, always follow `docs/guides/documentation-guide.md`.
4. Fill in the docs before starting implementation.

---

## 📂 How the Documentation is Used

| File | Purpose |
|---|---|
| `overview.md` | Explains what the project is and why it exists. |
| `architecture.md` | Explains how the system is structured. |
| `roadmap.md` | Lists the features in order, with their goal and status. |
| `instructions.md` | Tells the AI how to behave during the workflow. *(You can modify this file to adjust how the agent behaves.)* |
| `guides/documentation-guide.md` | Defines how documentation should be structured and reviewed. |

Feature-specific documentation is created under:

```text
/features/<feature-name>/
  spec.md
  tech.md
  tasks.md
```

---

## 📄 Document Skeletons Reference

Before drafting any core document, use the following guidelines exactly. Draft **one document at a time** and only after discussion and approval.

---

### 1. `overview.md`

**Purpose:** Define *what the system is* and *why it exists*.

**Skeleton:**

```md
# Overview

## Product
Short description of the system.

## Target Users
Who this is for.

## Problem
What problem it solves.

## Core Features
- Feature 1 (1 line)
- Feature 2
- Feature 3

## Constraints (Optional)
- Tech constraints
- Business rules
```

**Quality Criteria:**
- Clear in under 30 seconds
- No technical noise
- No implementation details

> ❌ Bad: Long explanations, mixing in architecture, deep feature flows.

---

### 2. `architecture.md`

**Purpose:** Define *how the system is structured* to guide the AI.

**Skeleton:**

```md
# Architecture

## Stack
- Frontend:
- Backend:
- Database:

## System Structure
Describe main parts:
- API server
- Client
- Database

## Data Flow
Simple description:
User → Frontend → API → Database → Response

## Core Entities
- User
- Payment
- etc.

## Key Decisions
- Auth method (JWT, sessions, etc.)
- API style (REST, GraphQL)
- State management approach

## Constraints
- Must use X
- Avoid Y
```

**Quality Criteria:**
- High-level, not code-level
- Defines patterns clearly
- Leaves little room for interpretation

> ❌ Bad: Too vague, too detailed, missing key decisions.

---

### 3. `roadmap.md`

**Purpose:** Control **order + status + scope** of features.

**Skeleton:**

```md
# Roadmap

## 1. Auth
Status: pending
Goal: User signup and login

## 2. Payments
Status: pending
Goal: Handle transactions

## 3. Dashboard
Status: pending
Goal: Display user data
```

**Status Options:** `pending` · `in development` · `completed`

> ❌ Bad: Adding specs, technical notes, brain dumps.

---

## 🛠 Project Starter Prompt

Use this prompt when starting a new project to create `overview.md`, `architecture.md`, and `roadmap.md`.

```text
I am working on a new project. We will brainstorm the project first, and at the end you will help me create the core project documentation.

Your tasks:
1. Ask clarifying questions to understand:
   - The purpose of the system
   - Target users
   - Core problems it solves
   - High-level features
   - Any constraints
2. Only after the discussion is complete, draft in chat the following documents:
   - overview.md
   - architecture.md
   - roadmap.md
3. Do NOT create any files yet. Wait for my approval before writing to the filesystem.
4. Keep the documents clear, concise, and follow the document skeletons below strictly.
5. Confirm understanding with me before drafting any document.

Start by asking me the first clarifying question needed to fully understand the project.

---

DOCUMENT SKELETONS REFERENCE

Before drafting any core document, use the following guidelines exactly. Draft one document at a time and only after discussion and approval.

---

1. overview.md

Purpose: Define what the system is and why it exists.

Skeleton:

  Overview

  Product
  Short description of the system.

  Target Users
  Who this is for.

  Problem
  What problem it solves.

  Core Features
  - Feature 1 (1 line)
  - Feature 2
  - Feature 3

  Constraints (Optional)
  - Tech constraints
  - Business rules

Quality Criteria:
- Clear in under 30 seconds
- No technical noise
- No implementation details

Bad: Long explanations, mixing in architecture, deep feature flows.

---

2. architecture.md

Purpose: Define how the system is structured to guide the AI.

Skeleton:

  Architecture

  Stack
  - Frontend:
  - Backend:
  - Database:

  System Structure
  Describe main parts:
  - API server
  - Client
  - Database

  Data Flow
  Simple description:
  User -> Frontend -> API -> Database -> Response

  Core Entities
  - User
  - Payment
  - etc.

  Key Decisions
  - Auth method (JWT, sessions, etc.)
  - API style (REST, GraphQL)
  - State management approach

  Constraints
  - Must use X
  - Avoid Y

Quality Criteria:
- High-level, not code-level
- Defines patterns clearly
- Leaves little room for interpretation

Bad: Too vague, too detailed, missing key decisions.

---

3. roadmap.md

Purpose: Control order, status, and scope of features.

Skeleton:

  Roadmap

  1. Auth
  Status: pending
  Goal: User signup and login

  2. Payments
  Status: pending
  Goal: Handle transactions

  3. Dashboard
  Status: pending
  Goal: Display user data

Status options: pending | in development | completed

Bad: Adding specs, technical notes, brain dumps.
```

---

## 🏁 Implementation Starter Prompt

Use this prompt after creating the `/Doc` folder in your project root.

```text
Read all files in `/Doc`, including `overview.md`, `architecture.md`, `roadmap.md`, `instructions.md`, and `guides/documentation-guide.md`.

Do NOT create any files yet.

Identify the next feature from `roadmap.md`.
Begin the feature design phase in chat only:
- Discuss the feature with me
- Clarify the purpose
- Clarify the user flow
- Clarify edge cases
- Clarify the implementation approach

Do NOT draft the feature spec until we have discussed it.
Do NOT create or modify any files during this phase.
When I approve the discussion, draft the full feature spec in chat only, using the structure from `guides/documentation-guide.md`:
- Feature Spec
- Technical Plan
- Task Breakdown

Wait for my explicit approval before writing anything to the filesystem.
Follow `instructions.md` exactly and do not skip any approval steps.
```

---

## 🤖 Working with AI

The AI should always:

- Read `overview.md`, `architecture.md`, `roadmap.md`, `instructions.md`, and `guides/documentation-guide.md`.
- Discuss each feature with you first.
- Wait for approval before creating or modifying any files.
- Follow the document standards exactly.