# icm-architect

Interpretable Context Methodology (ICM) workspace designer & auditor — folder structure as agent architecture.

Cross-platform plugin supporting:
- **Claude Code plugin**: `.claude-plugin/plugin.json`, `commands/icm.md`, `skills/icm-architect/`
- **Codex CLI plugin**: `.codex-plugin/plugin.json`, `skills/icm-architect/`
- **Antigravity / Gemini CLI plugin**: `plugin.json`, `gemini-extension.json`, `GEMINI.md`, `commands/icm.toml`, `skills/icm-architect/`

## Directory Structure
```
icm-architect/
├── .claude-plugin/
│   ├── marketplace.json
│   └── plugin.json
├── .codex-plugin/
│   └── plugin.json
├── assets/
│   └── templates/
├── commands/
│   ├── icm.md
│   └── icm.toml
├── references/
│   ├── core.md
│   ├── forms.md
│   └── system-map.md
├── skills/
│   └── icm-architect/
│       ├── SKILL.md
│       ├── assets/
│       └── references/
├── CONTEXT.md
├── GEMINI.md
├── LICENSE
├── README.md
├── SKILL.md
├── gemini-extension.json
└── plugin.json
```
