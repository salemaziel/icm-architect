---
name: icm-sync
description: Synchronize ICM routing tables and contracts with disk state to eliminate catalog drift.
---

Synchronize an ICM workspace's routing tables and contracts with the current filesystem layout.

Input: $ARGUMENTS

Follow the Sync Mode instructions in `skills/icm-architect/SKILL.md`:
1. **Scan Catalog vs. Disk**: Read root entry files (`HERMES.md`, `CLAUDE.md`, `AGENTS.md`, `GEMINI.md`) and root `CONTEXT.md`. Inventory all actual stage directories (`stages/*` or `NN_*`), record libraries, and shared folders.
2. **Detect Drift & Contract Gaps**:
   - Uncataloged stages (directories present on disk but missing in the routing table).
   - Dead catalog pointers (table rows pointing to deleted/renamed folders).
   - Contract gaps (stage folders missing an explicit `CONTEXT.md`).
   - Pipeline progress (derive current completion status by checking artifacts in each stage's `output/`).
3. **Reconcile Tables**: Show proposed routing table diffs. Update the routing tables in entry files and root `CONTEXT.md` cleanly, preserving user notes, identities, and custom rules.
4. **Scaffold Missing Contracts**: If stage directories lack a `CONTEXT.md`, offer to scaffold minimal contracts using `skills/icm-architect/assets/templates/stage-CONTEXT.md`.
5. **Walk Test**: Verify updated routing tables resolve and token budgets hold (2k-8k tokens per stage).
