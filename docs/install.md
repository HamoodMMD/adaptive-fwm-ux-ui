# Installation

A skill is just a folder. Put it where your agent looks for skills and keep the folder name `adaptive-fwm-ux-ui`.

| Agent | For all your projects | For one project only |
|---|---|---|
| **Claude Code** | `~/.claude/skills/adaptive-fwm-ux-ui/` | `.claude/skills/adaptive-fwm-ux-ui/` |
| **Codex** | `~/.agents/skills/adaptive-fwm-ux-ui/` | `.agents/skills/adaptive-fwm-ux-ui/` |
| **Other Agent Skills tools** | See your tool's documentation for its skills folder | |

macOS and Linux:

```bash
git clone https://github.com/HamoodMMD/adaptive-fwm-ux-ui.git ~/.claude/skills/adaptive-fwm-ux-ui
```

Windows (PowerShell):

```powershell
git clone https://github.com/HamoodMMD/adaptive-fwm-ux-ui.git "$HOME\.claude\skills\adaptive-fwm-ux-ui"
```

To update later, run `git pull` inside that folder.

It has no dependencies and needs no network access to run. Only `SKILL.md`, `references/` and `assets/` are used at run time.

---

[← Back to the main page](../README.md)
