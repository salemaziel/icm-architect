---
name: icm-bundle
description: Build an ICM Knowledge bundle from a brain dump, interviews, or transcripts and research.
---

Build an ICM Knowledge bundle: a body of knowledge one agent can walk.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

Follow Build mode in `SKILL.md` and the Knowledge bundle form in `references/forms.md`:
1. **Pick the variant.** If the material is transcripts, interviews, research or documents whose wording the bundle must keep (for a lecture, course, scripts or docs), also read `references/bundle-from-sources.md` and follow its pipeline where it replaces the Build steps. Otherwise build the plain bundle.
2. **Split factory from product.** How the person thinks and speaks (voice, principles, constraints) is the always-load layer; what they know about specific topics goes on shelves of linked notes, loaded by task.
3. **Scaffold from the templates.** `AGENTS.md` from `assets/templates/entry.md` plus the pointer files the owner's agents need, and a root `CONTEXT.md`. For the sources variant: `bundle-schema.md` to `_meta/schema.md`, `keep-out.txt` to `_meta/keep-out.txt`, the cards you need (`concept.md`, `source.md`, `plan.md`, `claim.md`) to `_templates/`, and `scripts/quotes.py`, `scripts/links.py` and `scripts/index.py` to `_tools/`.
4. **Write the notes.** Typed frontmatter, relative links, one idea per note. Never tidy or invent a quote: a quoted line must appear word for word in its source.
5. **Run the walk test.** A cold agent finds the person's principles, and their knowledge on a given topic, from `AGENTS.md` within a few reads and under about 8,000 tokens. For the sources variant, `python -I _tools/quotes.py` and `python -I _tools/links.py` pass.
