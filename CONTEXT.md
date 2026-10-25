# icm-architect

Interpretable Context Methodology (ICM) workspace designer and auditor: folder structure as agent architecture.

This fork of [RinDig/icm-architect](https://github.com/RinDig/icm-architect) packages the skill as a plugin:
- **Claude Code**: `.claude-plugin/plugin.json`, `commands/*.md`, `skills/icm-architect/`
- **Codex CLI**: `.codex-plugin/plugin.json`, `skills/icm-architect/`
- **Gemini CLI / Antigravity CLI**: `gemini-extension.json`, `plugin.json`, `GEMINI.md`, `commands/*.toml`, `skills/icm-architect/` (Antigravity loads `GEMINI.md` only from `rules/` and converts the commands to skills on install)
- **Hermes Agent**: `plugin.yaml`, `.hermes-plugin/plugin.json`, `HERMES.md`, `skills/icm-architect/`

## Where things live

| Path | What it holds |
|---|---|
| `SKILL.md`, `references/`, `assets/templates/`, `scripts/` | the skill, as upstream ships it plus the fork's Sync mode, Commands section and two references (`principles.md`, `paper.md`) |
| `skills/icm-architect/` | a copy of those four, which the plugin manifests load. Never edit it by hand: edit the root files and rerun the sync below |
| `commands/` | slash commands; each `.md` has a `.toml` twin with the same prompt (`$ARGUMENTS` becomes `{{args}}`) |
| `.claude-plugin/`, `.codex-plugin/`, `.hermes-plugin/`, `plugin.json`, `plugin.yaml`, `gemini-extension.json` | plugin manifests; keep their versions equal |

## Keeping the copy in sync

After any change to the root skill files:

```bash
rsync -a --delete --exclude '__pycache__' SKILL.md references assets scripts skills/icm-architect/
```

## Taking upstream changes

`git fetch upstream && git merge upstream/main`. Resolve the skill files toward upstream, re-apply the fork's additions, update `commands/` if forms, templates or scripts were renamed, rerun the sync, and bump the version in every manifest and in the vdw marketplace.
