---
name: central-memory-setup
description: Portable manual to install or repair a central, per-project routed memory system in OpenCode. Use it to replicate this setup on another machine or rebuild it.
---

# Central memory: portable setup

This skill is an **installation manual**, not the live memory.

Live memory belongs in `AGENTS.md` files (global and per folder), because OpenCode loads them automatically in every session. A skill is only read when invoked or when it fits the task: **it is not good for "always remember".**

## What it installs

- `~/central/GLOBAL_MEMORY.md`: history and central memory.
- `~/central/AGENTS.md`: routing rules when you open from `central`.
- `~/central/projects/<project>/AGENTS.md`: one per project (for example: web, trading, classes, automations).
- In `~/.config/opencode/AGENTS.md`: read `GLOBAL_MEMORY.md` on start, update the matching project, and create a folder when a new project appears.
- Optional: a `~/central/ideas/` folder for loose ideas, split by project, plus a general folder.

## Steps

1. Create the central folder and the `.md` files listed above.
2. In `GLOBAL_MEMORY.md` store: who the user is, projects, a short history, and the routing rule.
3. In `central/AGENTS.md` put:
   - read `GLOBAL_MEMORY.md`;
   - write to `projects/<name>/AGENTS.md` according to the project;
   - if a new project appears, create its folder and its `AGENTS.md`;
   - reflect anything important in the global memory too.
4. Add the section "Central memory and per-project routing" to `~/.config/opencode/AGENTS.md`.
5. Always open OpenCode from `~/central` (`cd ~/central && opencode`) so it loads the routing rules.
6. Check with: `find ~/central -maxdepth 3 -type f -o -type d | sort`.

## Choosing a model for file housekeeping

Sorting, moving and deleting files does not need a big model: use a lightweight one from those available in your install (list them with `/models`).

To pin it, there are two ways:

- A command with `model:` in the frontmatter: `~/.config/opencode/commands/quick.md`.
- A subagent with `model:` in the frontmatter: `~/.config/opencode/agents/quick.md`.

Without that, the model is picked from the UI with `/models`.

## Rules that do not change

- Never delete anything without the user's explicit confirmation.
- Answer in the user's language, direct and without needless jargon.
- Live memory always goes in `AGENTS.md`, never only in a skill.

---
Hagen AI Lab. Use it, modify it, share it freely.
