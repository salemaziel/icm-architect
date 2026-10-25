---
name: icm-pipeline
description: Build a sequential, human-gated folder pipeline for recurring workflows.
---

Build a sequential, human-gated folder pipeline using Interpretable Context Methodology (ICM).

Input: $ARGUMENTS

Follow the Pipeline form instructions in `skills/icm-architect/SKILL.md` and `skills/icm-architect/references/forms.md`:
1. **Dialogue Extraction**:
   - What is the repeating unit of work (e.g., episode, report, release, client deliverable)?
   - Walk through the sequence from input to final deliverable. Where does a human naturally stop to review or edit? (These become stage boundaries and human checks).
   - What reference material is stable across every run (brand voice, style rules, schemas, templates) vs. per-run inputs? (Split factory from product).
2. **Scaffold Directory Structure**:
   - Numbered stage folders: `stages/01_<name>/`, `stages/02_<name>/`, etc.
   - Each stage gets: `CONTEXT.md`, optional `references/`, and `output/`.
   - Factory folder: `_shared/` for voice, rules, and definition of done.
   - Setup folder: `setup/questionnaire.md` to configure the factory once.
3. **Write Stage Contracts**:
   - Use `skills/icm-architect/assets/templates/stage-CONTEXT.md`.
   - Explicit inputs: split into Working (`../<prev_stage>/output/<file>`) and Reference (`../../_shared/<rule>.md`).
   - Short numbered process steps.
   - One concrete Human Check (what a person inspects before downstream stages proceed).
4. **Write Root Routing**:
   - Create root entry file (`CLAUDE.md`, `HERMES.md`, `AGENTS.md`, or `GEMINI.md`) and root `CONTEXT.md` routing table.
5. **Run the Walk Test**:
   - Validate navigation, link resolution, and 2k–8k token limits.
