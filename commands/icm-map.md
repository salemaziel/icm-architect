---
name: icm-map
description: Create or query a System Map (objects, processes, change-impact) for a codebase or vault.
---

Create or query a System Map using Interpretable Context Methodology (ICM).

Input: $ARGUMENTS

Follow the System Map instructions in `skills/icm-architect/references/system-map.md` and `skills/icm-architect/SKILL.md`:

### Mode A: Build or Update System Map
If the input is a repository, folder, or empty (current workspace):
1. **Inventory**: Inspect codebase files, models, services, and core types. Do not slurp implementation code.
2. **Scaffold `map/` Structure**:
   - `map/CLAUDE.md`, `map/HERMES.md`, or `map/AGENTS.md` (map catalog routing).
   - `map/CONTEXT.md` (universes, clusters, naming conventions).
   - `map/_meta/schema.md` and `map/_templates/` (`object.md`, `process.md`).
   - `map/objects/` (record library of nouns/entities).
   - `map/processes/` (movements/runtime workflows).
   - `map/effects/CONTEXT.md` (change-impact index).
3. **Write Object Cards**:
   - One card per core entity using `skills/icm-architect/assets/templates/object.md`.
   - Include exact citations (`path:line`), relations (`owns`, `joins`, `looks-like-but-is-not`), and **Hits / Does not hit** impact lists.
4. **Write Process Cards**:
   - Runtime flows citing real entrypoints and sequences.
5. **Change-Impact Index (`effects/CONTEXT.md`)**:
   - Index: “if you change X, open these cards.”
   - Walk it backwards: identify what outside configs/jobs point in.
6. **Walk Test**: Validate cold-agent navigation and token budget.

### Mode B: Change-Impact Query
If the input asks about modifying a specific file, model, or component (e.g. `impact <target>` or `what hits <target>`):
1. Open `map/effects/CONTEXT.md` and the target's object card in `map/objects/`.
2. Follow the card's **Hits** and **Does not hit** sections and citations.
3. Report the exact impact waterfall, risks, and surfaces that must be checked, without reading the entire repository.
