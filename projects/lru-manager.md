# ⚙️ LRU Manager
*Least Recently Used position engine for project management*

## LRU Logic

### Position Rules
- **Position #1** = Most recently accessed project
- **Positions #2-10** = Other active projects in order
- **Position #11** = Automatically archived on next access/create

### On New Project
1. Create project file from template
2. Place at position #1
3. Shift all others down by 1
4. If a project reaches position #11 → move to `[type]-projects/archived/`

### On Load Project
1. Find project (active or archived)
2. If archived → move back to `[type]-projects/active/`
3. Move to position #1
4. Shift all others down by 1
5. If any reach #11 → auto-archive

### On Save Project
1. Update project file progress log
2. Keep current LRU position (save doesn't affect rank)
3. Update `project-list.md` with timestamp

## Capacity
- 10 active projects per type
- Unlimited archived projects
- Each type has independent LRU queue

## File Locations
- Active: `projects/[type]-projects/active/[name].md`
- Archived: `projects/[type]-projects/archived/[name].md`
- Overview: `projects/project-list.md`
- Templates: `projects/templates/[type]-template.md`
- Protocols: `projects/new-project-protocol.md`, `load-project-protocol.md`, `save-project-protocol.md`
