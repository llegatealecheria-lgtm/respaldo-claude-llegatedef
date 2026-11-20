# Llégate a Lechería — Gestión general de ClickUp — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Gestión de proyectos del equipo de IA en ClickUp, replicando estructuras validadas de Asana.

---

## Propósito
- Small team on AI-related projects
- Roles: Jera — project management and coordination; Angel — technical/AI development; Naylu — validation and approvals
- Primary workspace: ClickUp — Space "Espacio del equipo [ES-LA]", Space ID `90176234270`
- Asana also active, used as reference for structure and workflows
- ClickUp project management skills mirror validated Asana patterns

## Estado actual
- Migration of "IA Atención Clientes" from Asana to ClickUp 100% complete and verified — tasks, subtasks, dependencies, assignees, statuses, dates, descriptions and list names with emojis match
- Skill `clickup-gestor-de-proyectos` built and delivered: workspace mapping, project creation, reorganization, task management, filtering, automation recommendations as manual steps, status reports
- 9-list structure: 💡 Ideas → 🧠 Gestión → ✅ Validación → ⚙️ Desarrollo → 🧪 Pruebas → 🚀 Implementado, plus three personal task lists (one per team member)
- Pendiente: las instrucciones del proyecto mencionaban el nombre viejo `gestor-de-proyectos-clickup.skill` en vez de `clickup-gestor-de-proyectos.skill` — verificar
- Difficulty tags: `prioridad baja` (a few hours), `prioridad media` (3+ days, less than a week), `prioridad alta` (weeks or months)

## Herramientas
- ClickUp MCP — primary platform
- Asana MCP — structural reference; `get_project` with `include_sections: True` retrieves all sections in one call
- Skills: `clickup-gestor-de-proyectos` and `gestor-de-proyectos-asana`
- Palette: `#F2E5B3` (7499C crema) and `#FFC66E` (1355C) — backgrounds only
- Palette: `#65BBB0` (563C) and `#00607F` (7707C) — text, icons and shadows only; never backgrounds or card fills

---

## Detalles de la plataforma (aprendizajes)

### IDs de miembros
- Jera's correct ClickUp member ID: `222059093` (Jera Larez, jeralarez.05@gmail.com — con punto)
- ID `101260135` (jeralarez05@gmail.com, sin punto) is a wrong pending invite — never use it for assignments
- The bad invite must be cancelled manually in ClickUp workspace settings

### Limitaciones de API
- Recurring tasks and automations can't be created via ClickUp API — manual setup in the app
- `clickup_update_task` with `assignees: ['new_id']` replaces the full assignee array
- Asana subtask fields (`completed`, `assignee`, `due_on`) aren't reliably returned by `get_task` — fetch each subtask by GID

### Verificación
- Verify tag existence with an `add → remove` test on a known task — empty `filter_tasks` doesn't confirm absence
- Never infer ClickUp vs. Asana from task names — verify against UI or API responses
- Hidden tasks in "🚀 Listo / Implementado" are view behavior — enable "Show closed tasks" and expand parent toggles

### Empaquetado de skills
- Skill names lowercase with hyphens (e.g. `clickup-gestor-de-proyectos`); display titles in `SKILL.md` can be mixed case
- Workflow: `python -m scripts.package_skill [skill-name]` from `/home/claude`, copy the `.skill` to outputs, then present it
- If the `.skill` already exists in outputs, it can be re-presented without repackaging

---

## Forma de trabajo
- Max 1–2 clarifying questions before proposing a full structure
- No filler; bullet points
- Confirmation before team-visible bulk actions; direct execution for one-off requests
- Recommendations kept separate from objective status reports
- Validated design principles are not reopened unless Naylu asks
- New ClickUp structures mirror validated Asana structures, not generic templates
