---
name: icm
description: Design or restructure a workspace using Interpretable Context Methodology (ICM).
---

Design an ICM workspace or audit/restructure an existing workspace using Interpretable Context Methodology (ICM).

Input: $ARGUMENTS

Follow the instructions in `skills/icm-architect/SKILL.md`:
1. **Build Mode**: If starting from a described workflow or concept, interview the process, extract stages and human gates, select one of the six forms (Pipeline, Umbrella, Record library, Knowledge bundle, Context map, System map), scaffold the minimal directory structure using templates from `skills/icm-architect/assets/templates/`, write explicit contracts (`HERMES.md`, `CLAUDE.md`, `AGENTS.md`, `CONTEXT.md`), and run the walk test.
2. **Restructure Mode**: If auditing an existing workspace, take an inventory without moving files, classify files into the 5 roles (Catalog, Contract, Factory, Product, Dead), verify reference integrity, propose a migration map for approval, execute the migration, and validate with the walk test.
3. **Sync Mode** (`/icm sync` or `/icm-sync`): If reconciling an existing workspace after folders were added, moved, or renumbered, compare catalog routing tables with disk layout, reconcile missing or dead pointers, scaffold missing stage `CONTEXT.md` contracts, and run the walk test.

### Specialized Slash Commands
- `/icm-pipeline` — Build a sequential, human-gated folder pipeline.
- `/icm-map` — Create or query a codebase System Map (objects, processes, change-impact).
- `/icm-audit` — Audit an existing workspace with reference integrity checks.
- `/icm-sync` — Reconcile routing tables with disk layout to eliminate catalog drift.
- `/icm-walk` — Execute the cold-agent Walk Test to verify navigation and token limits.
- `/icm-graph` — Generate a Mermaid.js visual graph of the workspace pipeline or system map.
- `/icm-bundle` — Compile unstructured knowledge or expert interviews into a structured ICM Knowledge Bundle.
- `/icm-audit-ghosts` — Audit a system map and codebase to detect ghosts (missing code) and leftovers (unmapped code).
