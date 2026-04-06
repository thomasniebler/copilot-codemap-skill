# Copilot CODEMAP Skill

Reusable GitHub Copilot assets for a hierarchical repository navigation workflow built around `CODEMAP.md` files.

## What this repo contains

- `.github/skills/analyze-submodule-map/SKILL.md` - a skill that tells Copilot to read the root `CODEMAP.md`, then the nearest child map, then only the relevant source files
- `.github/prompts/setup-codemap.prompt.md` - a reusable prompt for setting up the CODEMAP hierarchy in another repository
- `snippets/copilot-instructions-snippet.md` - the instruction snippet to add to a target repository's `.github/copilot-instructions.md`

## How to reuse it

1. Copy the skill into `.github/skills/analyze-submodule-map/SKILL.md` in the target repository.
2. Copy the setup prompt into `.github/prompts/setup-codemap.prompt.md` in the target repository.
3. Add the instruction snippet from `snippets/copilot-instructions-snippet.md` to the target repository's `.github/copilot-instructions.md`.
4. Run the setup prompt to generate the repository's root and child `CODEMAP.md` files.

## Notes

This repository is the reusable source of truth for the skill assets. Copilot only treats the skill as active inside repositories that actually include the `.github/skills/` files locally.