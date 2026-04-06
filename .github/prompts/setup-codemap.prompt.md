---
agent: "agent"
description: "Set up a hierarchical code-map system for a repository"
---

Set up a reusable code-map system for this repository.

Follow this workflow:

1. Inspect the repository structure before creating any files.
2. Create a root `CODEMAP.md` that points to the major submodules and their responsibilities.
3. For each major submodule, create a scoped `CODEMAP.md` inside that submodule that explains the next level of structure without describing the whole repository again.
4. Add narrower child maps where a submodule is large enough to benefit from further decomposition.
5. Add a project skill in `.github/skills/` that tells Copilot to analyze a requested submodule by reading the root map, then the nearest submodule map, then only the relevant source files.
6. Update `.github/copilot-instructions.md` so the map-and-skill workflow is the default way to navigate the repository.
7. Add or update reusable prompts in `.github/prompts/` only when they help maintain the code-map system.
8. Validate that links between maps are correct and that the maps reflect the real repository structure.

Constraints:

- Keep each map scoped to its own directory or submodule.
- Prefer links to narrower maps over repeating the same content in multiple places.
- Make the prompt repository-agnostic so it can be copied into other repositories.
- Do not create planning notes outside the requested code-map files and prompt assets.
