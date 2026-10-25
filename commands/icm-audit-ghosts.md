---
name: icm-audit-ghosts
description: Audit an ICM System map against its tree: cards whose code is gone, stale universe marks, and code with no card.
---

Audit a System map against the tree it maps.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

Use the universes in `references/system-map.md`: live (in force), leftover (still present, no longer the main path), ghost (named or filed, not wired). The map never moves or writes the subject's files.
1. **Read the cards.** Every card under `map/objects/` and `map/processes/`; collect each `path:line` citation and each `universe:`.
2. **Ghosts.** A card whose cited file, type or function is gone or no longer wired. Never delete the card, since other cards link to it: propose `universe: ghost` and a note on the card saying what is gone, as of which commit.
3. **Universe drift.** A card marked live whose code is no longer the main path (propose leftover), or marked leftover or ghost whose code is in force again (propose live).
4. **Unmapped code.** Types, modules or files in the mapped clusters that have no card.
5. **Moves.** When a ghost and an unmapped file are the same thing moved, propose updating the card's citations instead of a new card.
6. **Run `python -I map/_tools/links.py`** if the map has it, and report any link that no longer resolves.

Report under "Ghosts", "Universe drift" and "Unmapped code", with a recommendation for each. Change nothing until the owner approves the report.
