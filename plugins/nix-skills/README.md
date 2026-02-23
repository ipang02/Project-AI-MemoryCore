# nix-skills
*Nix AI companion plugin — auto-triggered skills for Ipang*

## Plugin Info
- **AI Companion**: Nix
- **User**: Ipang
- **Version**: 1.0.0
- **Installed**: February 24, 2026

## Active Skills

| Skill | Trigger | Description |
|-------|---------|-------------|
| `save-memory` | "save", "save memory", "save progress" | Saves conversation insights to memory files |
| `save-diary` | "save diary", "write diary", "diary entry" | Documents session as structured diary entry |

## Adding New Skills

1. Create a new folder: `skills/[skill-name]/`
2. Create `SKILL.md` inside with YAML frontmatter + protocol
3. Done — skill auto-activates based on description field

Use `skill-format.md` as a reference template.

## Plugin Location
`plugins/nix-skills/`
