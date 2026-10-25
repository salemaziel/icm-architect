# icm-architect

Via Del Web extension for Gemini CLI and Antigravity CLI. It designs a process, idea or body of knowledge into an ICM (Interpretable Context Methodology) workspace, where folder structure is the agent architecture, or restructures an existing folder, repo or vault into one.

When a task is designing, restructuring, syncing, mapping or walking an ICM workspace, read `skills/icm-architect/SKILL.md` before acting. It routes to everything else.

## Commands

`/icm` picks the mode. Narrower: `/icm-pipeline`, `/icm-bundle`, `/icm-map`, `/icm-audit`, `/icm-audit-ghosts`, `/icm-sync`, `/icm-walk`, `/icm-graph`.

## The method in brief

- Numbered folders carry sequence, hierarchy carries context scope, plain markdown carries state.
- Three primitives: a **sequence** (numbered steps), a **shelf** (same-shaped files from one template), a **catalog** (a small file that points down).
- Five forms built from them: Pipeline, Record library, Knowledge bundle, Context map, System map.
- Every step ends at a check. A workspace enters through `AGENTS.md`; `GEMINI.md` in a workspace is a one-line pointer (`@./AGENTS.md`).
- One step loads its contract, references and inputs only: under about 8,000 tokens.
