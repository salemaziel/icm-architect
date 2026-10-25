# icm-architect

Interpretable Context Methodology (ICM) workspace designer & auditor — folder structure as agent architecture.

Cross-platform plugin supporting:
- **Hermes Agent**: `HERMES.md`, `plugin.yaml`, `.hermes-plugin/plugin.json`, `skills/icm-architect/`
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
├── .gemini-extension-install.json
├── .hermes-plugin/
│   └── plugin.json
├── assets/
│   └── templates/
├── commands/
│   ├── icm.md
│   ├── icm-audit.md
│   ├── icm-map.md
│   ├── icm-pipeline.md
│   ├── icm-sync.md
│   ├── icm-walk.md
│   ├── icm.toml
│   ├── icm-audit.toml
│   ├── icm-map.toml
│   ├── icm-pipeline.toml
│   ├── icm-sync.toml
│   └── icm-walk.toml
├── references/
│   ├── core.md
│   ├── forms.md
│   ├── paper.md
│   ├── principles.md
│   ├── reference-integrity.md
│   └── system-map.md
├── skills/
│   └── icm-architect/
│       ├── SKILL.md
│       ├── assets/
│       └── references/
├── CONTEXT.md
├── GEMINI.md
├── HERMES.md
├── LICENSE
├── README.md
├── SKILL.md
├── gemini-extension.json
├── plugin.json
└── plugin.yaml
```
