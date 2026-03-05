---
name: aquagarden-project
description: Continue work on the AquaGarden digital aquarium project in `/Users/friends/ai/aquagarden_2026_codex`. Use when Codex needs to plan, research, implement, verify, or hand off work for this specific project; when editing `index.html`, `AGENTS.md`, `PLAN.md`, `PROGRESS.md`, or project `references/`; or when coordinating aesthetic improvements, rendering changes, workflow docs, and multi-agent collaboration rules.
---

# AquaGarden Project

## Quick Start

1. Read `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`.
2. Read `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`.
3. Read `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`.
4. If the task is research-heavy, scan `/Users/friends/ai/aquagarden_2026_codex/references/`.
5. Choose the working command from [references/command-structure.md](references/command-structure.md).

## Core Workflow

### 1. Sync context

- Confirm the current file structure and the active app entrypoint.
- Treat `/Users/friends/ai/aquagarden_2026_codex/index.html` as the default implementation target.
- Keep the app browser-only unless the user explicitly asks for a stack change.

### 2. Route the request

- Use [references/task-routing.md](references/task-routing.md) to map the user request to the right command flow.
- Prefer one primary command at a time.
- If the request spans research plus implementation, split it into `research -> plan -> implement -> verify -> handoff`.

### 3. Execute with project priorities

Apply these priorities in order:

1. Preserve or improve contemplative visual quality.
2. Keep the scene readable and compositionally intentional.
3. Preserve smooth interaction and animation.
4. Avoid unnecessary structural complexity.

## Project Rules

- Prefer calm, natural, composition-led changes over flashy additions.
- Keep fish subordinate to the landscape unless the user explicitly asks otherwise.
- Update `/Users/friends/ai/aquagarden_2026_codex/PLAN.md` when priorities or task states change.
- Update `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md` at the end of substantive work.
- Update `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md` when workflow rules or project structure change.
- Save search-based findings into `/Users/friends/ai/aquagarden_2026_codex/references/`.
- Keep the single-file structure unless the user requests refactoring or `AQ-107` becomes active.

## Verify Before Hand-off

- Confirm the page loads in a browser.
- Check console errors.
- Check camera controls, lighting controls, animation continuity, and click interactions when relevant.
- Save a capture when the visual output changed materially.

## References

- [references/command-structure.md](references/command-structure.md)
- [references/task-routing.md](references/task-routing.md)
