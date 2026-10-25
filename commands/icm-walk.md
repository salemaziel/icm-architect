---
name: icm-walk
description: Run the cold-agent walk test on an ICM workspace and report what fails.
---

Walk an ICM workspace cold, as an agent with no memory, and report.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

Follow the walk test in `SKILL.md`; change nothing, only report:
1. **Orientation.** From `AGENTS.md` (or the pointer file the agent reads), can you say where you are and where to go for the current task within the entry file plus at most two more reads?
2. **Contracts.** Does every working folder have a `CONTEXT.md` naming exact input paths (working and reference), the job, the outputs, and a `## Check`?
3. **Status.** Can you state status purely from what is on disk: each `output/`, any `check.md` verdict, or a status line? A placeholder that only keeps a folder in git does not count.
4. **Catalog hygiene.** Does any routing file carry content? Is any fact stored in two places? Is any pointer file a second copy instead of a pointer?
5. **Links.** Run `python -I _tools/links.py` if the workspace has it; otherwise follow every link and input path you read. After a restructure, every reference that existed before the move must still resolve.
6. **Size.** Does one contract plus its inputs stay under about 8,000 tokens? Name any stage over it.
7. **Broken invariants.** Is each one explained where it breaks?
8. **Form checks.** Run the form's own checks from its reference. System map: can a cold agent answer *what is X* and *what moves if I change X* from `map/AGENTS.md` plus one card?

Report pass or fail per check, with the file to fix and the fix.
