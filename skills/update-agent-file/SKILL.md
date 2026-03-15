---
name: update-agent-file
description: Updates the CLAUDE.md or AGENTS.md file for a repository
---

Update the agent context file for this repository. Follow these steps:

**1. Determine the target file**
- Check if `CLAUDE.md` exists at the repository root
- If yes, update `AGENTS.md`
- If no, update `AGENTS.md` (create it if it doesn't exist)

**2. Gather information about the repository**

Before writing anything, explore the codebase thoroughly to understand:
- Primary language(s) and frameworks in use
- Build tool and how to run builds, tests, and linting
- Project structure — key folders and what lives where
- Any non-obvious conventions or things that could trip up an agent (deprecated folders, dual frameworks, generated files not to touch, etc.)
- Any existing architecture decisions or preferred libraries evident in the code

**3. Write or update the file**

Use the following structure. Only include sections where you have real, specific information — don't add placeholder sections or generic advice:

```markdown
# Project Overview
One or two sentences on what this project is and what it does.

## Architecture
Key architectural decisions, how the system is structured, and the rationale behind major choices.

## Tech Stack
- Language / runtime version
- Frameworks and key libraries
- Build tool

## Project Structure
Highlight any non-obvious folder layout or conventions.

## Development
How to build, run, and test the project locally.

## Coding Standards
Language-specific conventions, naming, formatting, and any linting rules enforced.

## Important Notes
Anything that would trip up an agent working in this codebase — deprecated paths, dual frameworks, files not to touch, etc.
```

**Rules**
- Be specific — every line should be something an agent couldn't figure out in 30 seconds of reading the code
- Keep it short — this file lives in context for every session, so every word costs something
- No generic advice (e.g. "write clean code") — only project-specific facts
- If updating an existing file, preserve any sections that are still accurate and update or remove anything outdated
- Do not add sections you don't have real content for
