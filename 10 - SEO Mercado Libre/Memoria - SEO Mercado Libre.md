# SEO Mercado Libre — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Publicaciones optimizadas para Mercado Libre de las propiedades de Llégate a Lechería.

---

## Resumen
- Objective: optimized, publication-ready Mercado Libre listing copy, consistent in format, tone and SEO strategy

## Voz y buyer personas
- Tone: "like that friend who gets you out of your routine" — warm but professional
- Personas: families, digital nomads, corporate executives, frequent tourists
- Origin markets: Caracas, Puerto Ordaz, El Tigre, Maturín, Anaco

## Diferenciadores
- Local host experience
- Guide service
- Starlink/fiber optic connectivity
- Self check-in

## Forma de trabajo
- Direct, informal Venezuelan Spanish
- Bullet-format responses
- Contradictions or missing data flagged explicitly, never filled with assumptions

## Estado actual
- Skill `mercadolibre-copywriter-seo` encodes business context, format rules and SEO logic
- Properties worked on: Tepui Caribe and Vientos de Mar (Pequeño)
- Apto. Doral Beach drafted, with two open items: classification (apartment vs. townhouse) and whether euro rates should be converted to USD for ML
- Titles depend on keyword research not yet documented in the skill — flag the gap and ask for the findings instead of improvising

---

## Formato aprobado (estricto)
1. Title header in all caps
2. Two highlight bullets
3. Short descriptive paragraph
4. "¿Qué ofrece este espacio?" — plain text bullets with all amenities together (no emojis, no sub-grouping)
5. Single closing line with reservation conditions

## Prohibido en el texto
- No emojis
- No emotional hooks
- No closing invitation to message via ML

## Políticas de ML
- External links and handles (Instagram, WhatsApp, Google Maps) in internal fichas must be removed — ML prohibits off-platform redirection

## Reglas del análisis de competencia (permanentes)
- Include square meters only if in the source data — never ask for it
- Specify security features precisely (e.g. "cercado eléctrico, portón eléctrico") — ask if missing
- Name specific nearby businesses instead of generic proximity — ask if missing
- Keep the "Beneficios" block from the internal Telegram bot ficha

## SEO
- ML weights word order; titles go from general to specific
- Keyword validation for Venezuela: `tendencias.mercadolibre.com.ve` (web panel only, no API)

---

## Herramientas y flujo
- Skill update protocol: when Naylu confirms a new rule or correction, update SKILL.md immediately and confirm it's saved
- Packaging: copy scripts to `/home/claude/pkgwork/` before running; YAML description needs block scalar syntax (`description: >`)
- Direct ML listing fetch is blocked by robots.txt; competitive research via search results and Airbnb listings as proxies
