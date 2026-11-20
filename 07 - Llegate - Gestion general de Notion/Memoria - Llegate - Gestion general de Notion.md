# Llégate a Lechería — Gestión general de Notion — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Arquitectura y mantenimiento del CRM de Notion.

---

## Propósito y alcance
- Naylu runs Llégate a Lechería, a vacation rental operation in Venezuela
- Claude acts as a dedicated Notion architect — executing CRM maintenance, schema changes, views and improvements directly via the Notion connector
- Scope covers all of Naylu's Notion work, including university projects and Visuarte

## Arquitectura
- Five interconnected pieces: Clientes, Pipeline Comercial, Reservas, Cartera de Propiedades, and a Dashboard Comercial page
- The Notion CRM is the source of truth; a separate external decision panel handles dynamic analysis and filtering
- Principle: no redesigns — integrate changes without breaking relations, rollups or formulas
- Dynamic analysis and filtering are deliberately out of scope for Notion

## Personas clave
- Angel — built Jera.IA, an AI agent that integrates with the CRM for property recommendations
- Jera.IA reads property and field names directly from the CRM, so any schema or naming change must be communicated to Angel proactively
- Schema changes are communicated to Angel via WhatsApp

## Estado (al momento de guardarse — verificar antes de usar)
- Global rename "Oportunidades" → "Recurrencias" across databases, rollups, relations and CRM manual text
- New Dashboard views: payment status Kanban (by Estado del pago), 📊 Rendimiento de Propiedades, 🌍 Clientes por Ciudad de Origen, 🔻 Embudo de Leads
- "Rango de Edad" formula field in Clientes with a table view (grouping by formula unsupported in Notion)
- "Prioridad Manual" checkbox in Cartera de Propiedades, shown in the main Table view, the Rotación de Propiedades Kanban and 📌 Prioridad Manual
- Bugs resolved: duplicate "Cliente" relation in Reservas removed, legacy "CRM — Propiedades" database removed, test records re-linked
- PENDIENTE: mensaje de WhatsApp para Angel sobre el cambio Oportunidades → Recurrencias (afecta a Jera.IA si consulta por nombre exacto)
- Dashboard audit: the Embudo table duplicates the Pipeline Kanban; Rendimiento de Propiedades overlaps with two property views
- Dashboard audit: Clientes Kanban and Rotación de Propiedades board lack GROUP BY settings
- Dashboard audit: three backup views in Clientes flagged for cleanup

## Próximos pasos
- Dashboard cleanup and deduplication
- Validate with Angel: Jera searches by WhatsApp before creating a client; Jera writes to the now-unique "Cliente" field in Reservas
- Multi-channel identifiers (Telegram, WhatsApp usernames) deferred until formats are confirmed
- Chart section deferred — the Notion free plan chart limit was a blocker
- Keep using the CRM and the skill for university and other projects

## Herramientas
- Notion + Notion MCP connector for direct execution
- Skill `arquitecto-de-notion`: `SKILL.md`, `references/mecanica-notion.md`, `references/sistema-llegate-a-lecheria.md` (frozen architecture reference)

---

## Mecánica del MCP de Notion (aprendizajes)

### Vistas
- `notion-create-view` with `parent_page_id` appends to the bottom of the page, outside toggles — moving into toggles is manual
- Views often report success without inserting — verify by fetching the parent page
- API board views group by "group" mode by default, not "option" mode; "group" mode on status fields fails to render
- Formula properties silently ignore `groupBy`
- No tool to delete individual views — only whole data sources via `in_trash`

### Fórmulas y consultas
- `ADD COLUMN FORMULA()` requires chained `or` operators, not `or(a, b, c)` (400 error)
- `notion-query-database-view` returns all properties regardless of `displayProperties`
- Formula and rollup columns can't be selected in SQL-style queries — infer from source data

### Límites del plan
- Free plan counts Chart views cumulatively — create/delete/recreate can still trigger the paywall
- Embedding views into Dashboard pages via text `update_content` is fragile and can corrupt sibling toggles

---

## Forma de trabajo
- Previews, impact assessments and clarifying questions before execution — no unilateral decisions
- Nothing delivered until it verifiably works
- One question at a time
- Direct execution when architecture decisions are already made
- Spanish throughout
- Bullets, comparative where useful, no filler

---

## Área: Llégate Manager
- Diseñando "Llégate Manager", sistema propio que integra CRM, disponibilidad centralizada, cotizaciones, reservas, finanzas, portal de propietarios e integraciones (WhatsApp, Instagram, TikTok, Google Calendar)
- Stack inicial: Lovable + React/TypeScript + Supabase; presupuesto de herramientas de unos USD 50–100 al mes
- Por fases (análisis → diseño funcional → construcción módulo por módulo → pruebas), sin conectar datos reales ni el WhatsApp operativo hasta aprobar pruebas
