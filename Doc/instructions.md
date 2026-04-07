# AI Development Instructions

## Core Principle
The chat is for design and discussion.
The codebase is the source of truth only after explicit user approval.

Never skip approval steps.

---

## Workflow Overview

### 1. Feature Design Phase (Chat Only)
- Discuss the feature with the user
- Clarify:
  - purpose
  - user flow
  - edge cases
  - implementation approach
- Do NOT create any files during this phase

---

### 2. Spec Generation (Chat Only)
When the user requests, generate a complete feature specification in chat.

Structure MUST be:

1. Feature Spec
2. Technical Plan
3. Task Breakdown

Rules:
- Do not introduce new ideas not discussed
- Consolidate all prior decisions clearly
- Keep it structured and concise

---

### 3. Approval Gate (Mandatory)
- Wait for explicit user approval
- Do NOT create or modify any files before approval

---

### 4. File Creation
After approval, create:

/features/<feature-name>/
  spec.md
  tech.md
  tasks.md

Rules:
- Follow existing patterns from other features
- Keep formatting consistent
- Do not add extra files

---

## Implementation Phase

### Task Execution
- Always work from tasks.md
- Execute ONE task at a time
- After completing a task:
  - mark it as complete
  - ensure it is functional before moving on

Do NOT:
- skip tasks
- combine multiple tasks at once
- jump ahead

---

### Testing
- Write tests alongside implementation
- Ensure core functionality works end-to-end
- Prefer simple, reliable tests over complex ones

After completing a feature:
- provide a clear test summary

---

## Documentation Rules

- spec.md = feature behavior (what)
- tech.md = implementation details (how)
- tasks.md = execution steps

Do NOT:
- duplicate information across files
- store feature specs in roadmap.md
- modify documentation without approval

---

### Referencing the Documentation Guide
- When documenting a new feature, always consult `guides/documentation-guide.md` (the documentation guide) to ensure spec.md, tech.md, and tasks.md follow the required structure and quality criteria.
- Do not invent sections or change formatting; the guide is the source of truth for how feature documentation should be written.
- If unsure about any section, ask for clarification rather than improvising.

## Updating Documentation

If implementation differs from the spec:

1. Identify the difference
2. Propose the update in chat
3. Wait for user approval
4. Then update the file

Never silently change documentation.

---

## Roadmap Rules

- roadmap.md is the source of truth for:
  - feature order
  - feature status
  - feature goals

You must:
- follow the order strictly
- never invent new features
- never reorder features

---

## Feature Completion

A feature is complete only when:
- all tasks are done
- tests pass
- user has validated functionality

Then:
- update roadmap.md status to "completed"

---

## Git Rules

- Do NOT commit automatically
- After completing a feature:
  - generate a commit message
  - wait for user approval before committing

---

## General Behavior Rules

- Prefer existing patterns over new ones
- Keep implementations simple
- Avoid unnecessary complexity
- Be consistent across features

Do NOT:
- make assumptions without confirmation
- introduce new tools/libraries without justification
- deviate from established structure

---

## Priority Order

Always prioritize:

1. User instructions
2. Approved specifications
3. Existing codebase patterns
4. These instructions

If conflicts arise, ask for clarification.