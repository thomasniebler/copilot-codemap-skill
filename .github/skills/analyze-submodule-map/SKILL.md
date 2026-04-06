---
name: analyze-submodule-map
description: Analyze a repository submodule by following the CODEMAP hierarchy first, then reading only the files the maps identify as relevant. Use this as the default navigation workflow for questions about backend code, frontend code, tests, docs, prompts, or other major repository areas.
---

# Analyze Submodule Map

Use this skill when the user asks how a part of the repository works, where a behavior lives, what the responsibilities of a submodule are, or how to navigate a specific area safely.

## Goal

Understand a requested submodule by reading the nearest `CODEMAP.md` files before reading implementation files, so navigation stays scoped and repeatable.

## Inputs

- a submodule path such as `src/janus/`, `src/janus/api`, `frontend/src/components`, `tests/`, or `.github/`
- or a natural-language target such as "the FastAPI routers", "the dashboard pages", "the migration history", or "the Copilot prompts"

## Workflow

1. Start with the repository root `CODEMAP.md`.
2. Resolve the requested area to the most relevant submodule.
3. Open that submodule's `CODEMAP.md`.
4. Follow child-map links only when they narrow the task further.
5. Read the implementation files named by the selected map.
6. Read tests for the same area when behavior, contracts, or edge cases matter.
7. Stop expanding scope once you can answer the question with confidence.

## Analysis output

When you respond, include:

1. **Scope** - which submodule map you used
2. **Responsibilities** - what that area owns
3. **Key files** - the main files or child maps worth reading next
4. **Important flows** - request flow, data flow, or state flow inside that area
5. **Hotspots** - risky or coupling-heavy files to treat carefully

## Rules

- Prefer map-guided reading over broad repository-wide searching.
- Do not jump straight to random source files when a relevant `CODEMAP.md` exists.
- If the existing maps are incomplete or clearly stale, say so explicitly and then continue with targeted source inspection.
- If the task spans multiple top-level submodules, read the root `CODEMAP.md` again before crossing boundaries.

## Example triggers

- "Analyze the FastAPI router package"
- "How is the frontend component tree organized?"
- "Where should I make a change for reminder extraction?"
- "Explain the Copilot prompt setup in this repo"
