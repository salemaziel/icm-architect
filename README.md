# icm-architect

A Claude skill that designs any process, idea, or problem into an **ICM workspace** — folder structure as agent architecture — or restructures an existing folder, repo, or vault into one.

ICM (Interpretable Context Methodology) replaces orchestration code with structure: numbered folders carry sequencing, hierarchy carries context scoping, plain markdown files carry state. One agent, reading the right files at the right moment, does the work of a multi-agent framework — and a human can open any folder and see exactly what state the system is in.

The workspace is a library. The routing files are the catalog: small, stable, they point at everything and store almost nothing. One librarian — one model — walks the building, and the question decides which shelf gets walked to.

- Paper: [Interpretable Context Methodology: Folder Structure as Agent Architecture](https://arxiv.org/abs/2603.16021) (Van Clief & McDermott)
- Community: [Clief Notes](https://www.skool.com/cliefnotes)

## What it does

Two modes:

- **Build** — extracts the structure already present in how you describe your work (the stages, the human gates, what's stable vs. per-run), picks one of six proven forms, and scaffolds the smallest workspace that carries it.
- **Restructure** — audits an existing folder, classifies every file (catalog / contract / factory / product / dead), proposes a migration map for approval, then migrates and validates.

Six forms, one skeleton: **Pipeline** (production line), **Umbrella** (portfolio of pipelines), **Record library** (people/clients/sessions), **Knowledge bundle** (a navigable brain), **Context map** (an organization as a graph), **System map** (a folder later agents will edit — nouns, movements, change-impact). They compose and recurse.

Every result is validated with the **walk test**: an agent with no memory must orient, act, and report status from the files alone.

## Install

### VDW Marketplace (Recommended)
Register the VDW marketplace once, then install:

```bash
# Claude Code
claude plugin marketplace add https://github.com/salemaziel/vdw-claude-plugins
claude plugin install icm-architect@vdw

# Codex CLI
codex plugin marketplace add https://github.com/salemaziel/vdw-claude-plugins
codex plugin add icm-architect@vdw

# Gemini CLI / Antigravity CLI
gemini extension registry add https://github.com/salemaziel/vdw-claude-plugins
gemini extension install vdw-claude-plugins/icm-architect
```

### Direct Plugin / Skill Install

**Claude Code:**
```bash
claude plugin install https://github.com/salemaziel/icm-architect
# Or copy to ~/.claude/skills/icm-architect/
```

**Codex CLI:**
```bash
codex plugin add https://github.com/salemaziel/icm-architect.git
```

**Gemini CLI / Antigravity CLI:**
```bash
gemini extension install https://github.com/salemaziel/icm-architect
# Or enable via agyplugins:
# agyplugins enable icm-architect
```

**Claude apps:** upload `icm-architect.skill` (build it with the skill-creator packager, or zip this folder's contents) via Settings → Capabilities.

## Layout

```
icm-architect/
├── .claude-plugin/
│   ├── marketplace.json     # Claude marketplace descriptor
│   └── plugin.json          # Claude Code plugin manifest
├── .codex-plugin/
│   └── plugin.json          # Codex CLI plugin manifest
├── assets/templates/        # Copyable starters: CLAUDE.md, CONTEXT.md, stage contracts, etc.
├── commands/
│   ├── icm.md               # Claude Code slash command (/icm)
│   └── icm.toml             # Gemini / Antigravity CLI custom command (/icm)
├── references/
│   ├── core.md              # Five principles, five-layer hierarchy, naming, token discipline
│   ├── forms.md             # The six forms in depth: skeletons, moves, failure modes
│   └── system-map.md        # Audit pipeline for the System map form
├── skills/
│   └── icm-architect/       # Multi-platform skill bundle
│       ├── SKILL.md
│       ├── assets/
│       └── references/
├── CONTEXT.md               # Workspace context
├── GEMINI.md                # Gemini / Antigravity extension context
├── LICENSE
├── README.md
├── SKILL.md
├── gemini-extension.json    # Gemini CLI extension manifest
└── plugin.json              # Antigravity CLI plugin manifest
```

MIT licensed, like the protocol it serves.
