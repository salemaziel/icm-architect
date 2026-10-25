---
name: icm-graph
description: Draw an ICM workspace (or several) as a graph with the skill's links.py and viz.py scripts.
---

Draw an ICM workspace as an interactive graph.

Use the `icm-architect` skill; load it if it isn't loaded. Paths below are relative to the skill's folder, except paths in the workspace being worked on.

Input: $ARGUMENTS

1. **Find the tools.** If the workspace has no `_tools/links.py` or `_tools/viz.py`, offer to copy them from `scripts/`; they are standard-library Python 3.
2. **Write the graph.** `python -I _tools/links.py --graph _tools/graph.jsonl`. It also lists every link that does not resolve; report those.
3. **Draw it.** `python -I _tools/viz.py _tools/graph.jsonl -o viz.html`. Name several graph files to draw several workspaces together. The page loads its libraries from a CDN, so viewing it needs the internet.
4. **No Python?** This fallback is this plugin's addition, not part of the method: write a Mermaid `flowchart LR` to `visual-map.md` instead: stages or cards as nodes, inputs, `consumes:` / `produces:` and **Hits** as edges, reference inputs dashed. Draw only links that are written in the files; never infer one.
