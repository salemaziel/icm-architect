# icm-architect

A multi-agent skill and plugin that designs any process, idea, or problem into an **ICM workspace** — folder structure as agent architecture — or restructures an existing folder, repo, or vault into one.

ICM (Interpretable Context Methodology) replaces orchestration code with structure: numbered folders carry sequencing, hierarchy carries context scoping, plain markdown files carry state. One agent, reading the right files at the right moment, does the work of a multi-agent framework — and a human can open any folder and see exactly what state the system is in.

The workspace is a library. The routing files are the catalog: small, stable, they point at everything and store almost nothing. One librarian — one model — walks the building, and the question decides which shelf gets walked to.

- Paper: [Interpretable Context Methodology: Folder Structure as Agent Architecture](https://arxiv.org/abs/2603.16021) (Van Clief & McDermott)
- Community: [Clief Notes](https://www.skool.com/cliefnotes)

## What it does

Three modes:

- **Build** — extracts the structure already present in how you describe your work (the stages, the human gates, what's stable vs. per-run), picks one of six proven forms, and scaffolds the smallest workspace that carries it.
- **Restructure** — audits an existing folder, classifies every file (catalog / contract / factory / product / dead), verifies reference integrity, proposes a migration map for approval, then migrates and validates.
- **Sync** (`/icm sync` or `/icm-sync`) — reconciles routing tables and contracts with disk state to eliminate catalog drift when folders are added, moved, or renumbered.

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

# Hermes Agent
hermes skills install https://github.com/salemaziel/icm-architect
```

### Direct Plugin / Skill Install

**Hermes Agent:**
```bash
# Install as skill
hermes skills install https://github.com/salemaziel/icm-architect
# Or link directly into your Hermes skills directory:
# ln -s $(pwd)/skills/icm-architect ~/.hermes/skills/icm-architect
# Or trust in project:
# hermes skills trust .
```

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
├── .hermes-plugin/
│   └── plugin.json          # Hermes Agent plugin descriptor
├── assets/templates/        # Copyable starters: HERMES.md, CLAUDE.md, AGENTS.md, CONTEXT.md, stage contracts, etc.
├── commands/
│   ├── icm.md               # Claude Code master command (/icm)
│   ├── icm-pipeline.md      # Claude Code pipeline builder (/icm-pipeline)
│   ├── icm-map.md           # Claude Code system map & change impact (/icm-map)
│   ├── icm-audit.md         # Claude Code restructure & reference integrity (/icm-audit)
│   ├── icm-sync.md          # Claude Code catalog drift sync (/icm-sync)
│   ├── icm-walk.md          # Claude Code cold-agent walk test (/icm-walk)
│   ├── icm.toml             # Gemini / Antigravity CLI command (/icm)
│   ├── icm-pipeline.toml    # Gemini / Antigravity CLI command (/icm-pipeline)
│   ├── icm-map.toml         # Gemini / Antigravity CLI command (/icm-map)
│   ├── icm-audit.toml       # Gemini / Antigravity CLI command (/icm-audit)
│   ├── icm-sync.toml        # Gemini / Antigravity CLI command (/icm-sync)
│   └── icm-walk.toml        # Gemini / Antigravity CLI command (/icm-walk)
├── references/
│   ├── core.md              # Five principles, five-layer hierarchy, naming, token discipline
│   ├── forms.md             # The six forms in depth: skeletons, moves, failure modes
│   ├── reference-integrity.md # Move-safety gate: reference audit, case-folding, copy-verify-remove
│   └── system-map.md        # Audit pipeline for the System map form
├── skills/
│   └── icm-architect/       # Multi-platform skill bundle
│       ├── SKILL.md
│       ├── assets/
│       └── references/
├── CONTEXT.md               # Workspace context
├── GEMINI.md                # Gemini / Antigravity extension context
├── HERMES.md                # Hermes Agent native context
├── LICENSE
├── README.md
├── SKILL.md
├── gemini-extension.json    # Gemini CLI extension manifest
├── plugin.json              # Antigravity CLI plugin manifest
└── plugin.yaml              # Hermes Agent plugin manifest
```

MIT licensed, like the protocol it serves.
