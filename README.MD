# 🚀 Project README

This repository is designed to support an **AI-assisted development workflow**. The documentation in `/ai` helps you define the project clearly, keep the AI aligned, and reduce confusion during implementation.

---

## 📝 Setup Instructions

1. Copy the entire `/ai` folder into the root of your project.
2. Fill in the core documents before starting implementation:
   - `overview.md`
   - `architecture.md`
   - `roadmap.md`
3. `instructions.md` is already configured - modify it to adjust how the AI agent behaves.
4. When using AI to write documentation, always follow `ai/guides/doc-standards.md`.

---

## 📂 How the Documentation is Used

| File | Purpose |
|---|---|
| `overview.md` | Explains what the project is and why it exists. |
| `architecture.md` | Explains how the system is structured. |
| `roadmap.md` | Lists the features in order, with their goal and completion status. |
| `instructions.md` | Tells the AI how to behave during the workflow. |
| `guides/doc-standards.md` | Defines standards for all documentation. |
| `guides/feature-standards.md` | Defines standards for feature-specific docs. |

### Folder Structure

```
/ai
  overview.md          # High-level project description
  architecture.md      # System architecture and design decisions
  roadmap.md           # Feature order, goals, and status tracking
  instructions.md      # AI instructions and workflow rules
  guides/
    doc-standards.md   # Documentation standards
    feature-standards.md
  dependencies/        # Controlled dependency knowledge
    <dependency-name>/
      docs.md          # Fetched official docs for that dependency
  features/            # Feature-specific documentation
    <feature-name>/
      spec.md          # What the feature does
      tech.md          # How the feature will be built
      tasks.md         # Task breakdown for execution
```

---

## 🏁 Getting Started

### Phase 1: Define the Project

Use this prompt to create `overview.md`, `architecture.md`, and `roadmap.md`:

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
4. Keep the documents clear, concise, and follow the document skeletons in ai/guides/doc-standards.md
5. Confirm understanding with me before drafting any document.

Start by asking me the first clarifying question needed to fully understand the project.
```

---

### Phase 2: Implement Features

Use this prompt after filling in the core documents:

```text
Read all files in `/ai`, including overview.md, architecture.md, roadmap.md, instructions.md, and guides/doc-standards.md.

Do NOT create any files yet.

Identify the next feature from roadmap.md.
Begin the feature design phase in chat only:
- Discuss the feature with me
- Clarify the purpose
- Clarify the user flow
- Clarify edge cases
- Clarify the implementation approach

Do NOT draft the feature spec until we have discussed it.
Do NOT create or modify any files during this phase.
When I approve the discussion, draft the full feature spec in chat only, using the structure from ai/guides/feature-standards.md:
- Feature Spec
- Technical Plan
- Task Breakdown

Wait for my explicit approval before writing anything to the filesystem.
Follow ai/instructions.md exactly and do not skip any approval steps.
```

---

## 🤖 Working with AI

The AI should always:

1. Read all files in `/ai` before starting work
2. Follow `ai/instructions.md` for workflow rules
3. Discuss each feature before implementing
4. Wait for approval before creating or modifying files
5. Use `ai/guides/doc-standards.md` and `ai/guides/feature-standards.md` for documentation
6. Fetch and save dependency docs to `ai/dependencies/<name>/docs.md` before using new libraries

---

## 📋 Document Quick Reference

For full skeletons and quality criteria, see:
- Core docs (`overview.md`, `architecture.md`, `roadmap.md`) → `ai/guides/doc-standards.md`
- Feature docs (`spec.md`, `tech.md`, `tasks.md`) → `ai/guides/feature-standards.md`
