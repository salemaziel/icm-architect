---
name: icm
description: Design or restructure a workspace using Interpretable Context Methodology (ICM).
---

Design a new ICM workspace, or restructure or sync an existing one.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

Read `SKILL.md`, then pick the mode from the input:
1. **Build**: a described workflow, idea or problem. Extract the stages and checks from dialogue, pick a form from `references/forms.md` (Pipeline, Record library, Knowledge bundle, Context map, System map, or a recipe over the three primitives), scaffold the smallest structure from `assets/templates/`, write `AGENTS.md`, the pointer files the owner's agents need and the contracts, then run the walk test.
2. **Restructure**: an existing folder, repo or vault. Inventory without moving anything, classify every file into the five roles, find what points at each file, propose a migration map and wait for approval, then copy, verify and remove, and run the walk test.
3. **Sync** (`/icm sync`): an existing ICM whose folders were added, moved or renumbered. Follow Sync mode.

If the input does not make the mode clear, ask.

Narrower commands: `/icm-pipeline`, `/icm-bundle`, `/icm-map`, `/icm-audit`, `/icm-audit-ghosts`, `/icm-sync`, `/icm-walk`, `/icm-graph`.
