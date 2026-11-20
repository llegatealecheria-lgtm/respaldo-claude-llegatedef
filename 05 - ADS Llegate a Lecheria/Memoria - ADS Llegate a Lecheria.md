# ADS Llégate a Lechería — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Campañas de Meta Ads de Llégate a Lechería.

---

## Forma de trabajo

- Prefers direct, jargon-free explanations with plain-language analogies for CPL, CTR, CPM and frequency
- Evaluates tools and prompts in a new chat before integrating them into the skill
- Corrects forward-looking language for actions already completed; prefers a changelog/bitácora format for executed changes

## Formato de reportes
- HTML with brand tokens: teal `#65BBB0`, mango `#FFC66E`, cream `#F2E5B3`, deep blue `#00607F`
- Sections: hero header, KPI grid, what-we-know/don't-know grid, creative audit table with status tags, diagnosis, decision cards, next experiment
- Glossary with plain-language analogies for CPL, CTR, CPM and frequency
- Decision cards: evidence / hypothesis / risk / alternative

## Registro de cambios y evaluación
- Dated bitácora entries appended to the relevant Notion campaign page: change number, rationale, follow-up reminders
- Creative evaluation cross-referenced against prior Notion logs, the master strategy document and the latest evaluation before any recommendation

## Notion — IDs y estructura
- META ADS PLANNER TEMPLATE: `6c5eb89c87eb836da81c013c23210f37`, under "Marketing Space"
- ⛽ Campañas: `collection://a08eb89c-87eb-827d-b1fc-07b152f9750c`
- C1 · Vacacional MOFU: `7a8eb89c87eb8212be46013198c3fcc3` (el ID viejo `386c1b5c3edb8116a3d1dd1e0a5fda00` da 404, no usar)
- C2 · Vacacional TOFU: `559eb89c87eb82b3809901a55929a134`
- C3 y C4 (posiblemente desactualizados, verificar): `386c1b5c3edb81de9e2fddea6786c536`, `386c1b5c3edb812fb37cfe5f210036a5`
- Fetching by page ID is more reliable than Notion search for campaign rows
- Appending: `notion-update-page` with `command: insert_content`, `position: {type: end}`; dollar signs need escaping (`\$`)
- Large structured blocks: `old_str` must match exactly; `replace_content` on full sections is more reliable than `update_content` with escaped characters in tables

## Otras herramientas
- Google Calendar under `llegatealecheria@gmail.com`; events in `America/Caracas`, popup reminders, optional email reminders 720 minutes ahead for key checkpoints
- Meta Ads Manager exports processed via Excel uploads; the ad set name column has been missing in recent exports — flag it when it affects audience analysis
- Desde nov 2026 Meta Ads está conectado a Claude vía Windsor.ai (cuenta CP2 Llegate a Lecheria), para leer datos directo sin exportar Excel
- Cada cambio que cuente (anuncios apagados, rotaciones) se registra en la bitácora de Notion; la base ⛽ Campañas se mantiene depurada con las campañas realmente activas en Meta
- The `meta-ads-trafficker` skill contains `report_html_guide.md` (brand tokens, typography, simplification rules, analogies, improvement log) and `SKILL.md`
- The Claude Project stores dynamic data (prompt banks, campaign history, buyer personas, brand brief) separately from the skill
- Reservations also tracked in "Base de datos llegate 2026 Responses" with a "Red social" field; Meta Ads bookings are under-tagged there (often "Instagram" instead of "ADS Instagram"), so ad-attributed counts likely undercount — cross-check cautiously

---

## Aprendizajes de Meta Ads

### Estructura y presupuesto
- CBO outperformed ABO: more conversations at roughly half the CPL. ABO became unaffordable due to Meta's $2/day per-ad-set minimum at this budget level; reverting to CBO was the recommendation
- Changing budget structure mid-campaign resets the learning phase — minimize structural changes
- Switching a published Advantage+ (Messages) campaign from CBO to ABO requires duplicating the campaign
- Advantage+ placements don't allow deselecting channels (e.g. Messenger); solution: duplicate the ad set with manual placements
- Scaling: 10–20% weekly at CBO level, 10% floor when the remaining window is short or in a scarcity phase

### Datos y reportes
- Editing a live post caption blends historical CPL — evaluate from the edit date forward, never cumulative
- Deleted ad set data is still accessible by filtering reports to include deleted entities; a duplicated ad set restarts learning from zero

### Marco de evaluación
- Three layers: industry benchmarks, historical data as comparison (not validation), current context — past performance is not assumed optimal
- "Stop analysis" rules shouldn't be rigid — the skill guides thinking, not a fixed output

### Creativos
- "Reducing a creative's budget share" is done by adding a stronger competing creative to the same ad set
- Audience overlap between C1 and C2 is intentional given the funnel strategy
- Two-wave approach: priority assets on day 1, apartment-specific content in week 2 based on CTR thresholds
- Max 4–5 active creatives per ad set at this account's budget levels

---

## Área: Escuela Llégate
- Espacio en Notion "Escuela Llegate a Lecheria" para formaciones del negocio; dentro, la página "Meta Ads formaciones" (nov 2026) con lo aprendido en las asesorías de Meta Ads con Adrián

## Área: Estrategia de embudo de la próxima campaña
- (nov 2026) Estrategia en 3 etapas: TOFU (público frío, contenido orgánico existente o nuevo de Instagram), MOFU (público tibio: intereses + públicos similares de la data de Instagram) y retargeting (venta directa a públicos personalizados y base de datos)
