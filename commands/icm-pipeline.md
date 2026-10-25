---
name: icm-pipeline
description: Build a numbered folder pipeline for a recurring workflow, with a check at the end of every stage.
---

Build an ICM Pipeline: numbered stages, each ending at a check.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

Follow Build mode in `SKILL.md` and the Pipeline form in `references/forms.md`:
1. **Extract the structure from dialogue.** Ask a few at a time: what is the repeating unit of work; walk through one run start to finish, and where does the person stop to check something; what stays the same every run and what is new each run; what artifact leaves the workspace when it is done.
2. **Scaffold the smallest structure.** `stages/01_<name>/`, `stages/02_<name>/`, ... each with a `CONTEXT.md` and an `output/`; `_shared/` for the factory; `_templates/`; `_tools/` with `scripts/links.py` copied in; `setup/questionnaire.md` only if the factory needs configuring per user. No folders for stages that do not exist yet.
3. **Write each stage contract** from `assets/templates/stage-CONTEXT.md`: exact input paths split into working (`../<previous stage folder>/output/<file>`) and reference (`../../_shared/<file>.md`), numbered process steps, outputs, and a `## Check` naming who or what checks. A check that is not a person writes `check.md` beside the output: `pass`, or `fail: <why>`.
4. **Write the routing.** `AGENTS.md` from `assets/templates/entry.md`, a one-line pointer file for each agent the owner uses that reads another name (`references/core.md`, Naming), and root `CONTEXT.md` from `assets/templates/CONTEXT.md`.
5. **Run the walk test**, including `python -I _tools/links.py`.
