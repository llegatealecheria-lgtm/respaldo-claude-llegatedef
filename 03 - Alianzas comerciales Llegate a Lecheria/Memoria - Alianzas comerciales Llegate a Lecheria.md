# Alianzas comerciales Llégate a Lechería — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Alianzas con agencias de viajes y restaurantes para la plataforma de estadías cortas corporativas.

---

## Resumen

- Naylu is the founder and operator of "Llégate a Lechería", a vacation and corporate short-stay rental platform based in Lechería, Estado Anzoátegui, Venezuela
- The platform serves corporate clients — executives, consultants, temporary work teams — with professional temporary lodging packages
- Actively expanding into bundled gastronomic services to generate additional margin on food coordination

## Personas clave
- Jera — sales advisor who currently receives commissions on bookings
- Monzer — owner of Kleyopatra (Arabic restaurant), a confirmed gastronomic partner who accepted the alliance proposal
- El Nacional and La Casona — additional restaurant partners with confirmed or near-confirmed agreements
- A travel agency — prospective commercial alliance partner currently in pitch/negotiation phase

## Marca
- Brand palette is strictly teal `#65BBB0`, gold `#FFC66E`, cream `#F2E5B3`, navy `#00607F`, white
- Black is not a brand color
- Logo requires transparent PNG for clean placement on colored backgrounds

## Estado — pitch a la agencia de viajes
- A complete 10-slide travel agency pitch deck (.pptx) has been built using real property data, brand assets, and validated pricing
- Tiered commission structure proposed to the agency: 10% base, 12% at ~20 guaranteed nights/month, 15% at ~40 guaranteed nights/month
- On agency-referred bookings, Jera and the agency each receive 10% (split from the 20% previously allocated entirely to Jera), keeping Naylu's net per night at baseline
- Separate structure for one-time property owner referrals: Jera 15%, referring owner 10%
- Jera has not yet been informed of the commission restructuring
- Volume guarantees have not yet been discussed with the agency
- Notion page "💰 Tus Comisiones — Agencias y Referidos" exists as a child of the CRM page, framed from Jera's perspective (her earnings per scenario, no internal margins exposed)
- CRM parent Notion page ID: `377eb89c-87eb-8073-b9a8-f8f050aeda2d`
- Commission Notion page ID: `3a6eb89c-87eb-8174-95c2-cf035bc539ad`

## Estado — alianzas con restaurantes
- Kleyopatra: menu finalized at 16 dishes across 4 categories; corporate pricing negotiated with Monzer
- Flat prices per category requested from Kleyopatra: $11 almuerzo estándar, $15 almuerzo premium, $10 cena estándar, $15 cena premium
- El Nacional: breakfast $7/person, executive lunch $13/person, dinner $7/person pending menu confirmation; delivery within Lechería is free
- A 15% operational margin is embedded in El Nacional's final package price and not disclosed to the end client
- La Casona: three-tier structure (Casero, Estándar, Premium) for lunch and dinner, with 15% margin applied
- La Casona open items: delivery terms, IVA treatment, and beverage inclusion still pending

## Próximos pasos
- Communicating the commission restructuring to Jera
- Finalizing volume guarantee discussions with the travel agency
- Confirming remaining open items with La Casona (delivery, IVA, beverages)
- Confirming El Nacional's dinner menu
- Potentially formalizing the gastronomic pricing across all three restaurant partners into a unified package framework
- Quiere ofrecer a empresas un "kit de abastecimiento ejecutivo" dentro de las cotizaciones corporativas (como el kit hecho con Blessing Travel): comidas estándar de desayuno (pan, jamón, queso amarillo, mozzarella) y cosas prácticas para que el empleado se las arregle dentro del apartamento

---

## Forma de trabajo

### Principios
- Analysis before execution: validate numbers and logic first, then produce materials
- Expenses are variable, not fixed: monthly operating expenses come from dedicated ingreso/egreso sheets (e.g. "Marzo ingresosegresos"); revenue comes from monthly booking sheets
- Commission structures expressed as minimum guaranteed percentages, not fixed dollar minimums per booking
- Margins are embedded, not disclosed: the 15–18% operational margin on gastronomic services is built into the package price and never communicated to the end client
- 18% is recommended as a starting margin, leaving room to negotiate down
- Supplier negotiation: let the supplier quote first before revealing price targets
- Framing for internal stakeholders: the Notion commission page was framed from Jera's earnings perspective
- Seafood is a strategic differentiator: Lechería is coastal, so dishes like Linguini Fruto di Mare are kept even if they complicate standardization

### Preferencias
- Direct, conversational WhatsApp language — short and human-sounding, not formal or robotic
- When given too much analysis, simplify to a single clear recommended action
- Works iteratively: validates data → builds assets → refines with corrections in real time
- Uses real booking data (multi-sheet Excel with monthly tabs) as the authoritative source for financial modeling
- Produces branded outputs: pitch decks, minutas, Notion pages, WhatsApp messages

### Herramientas
- Notion — CRM and documentation hub; child pages for partner-specific content
- Notion operations that work: `notion-update-page` with `replace_content` and `update_properties` as separate calls; child pages via `parent: {type: 'page_id', page_id: '...'}`
- Excel multi-sheet workbook — inventory and booking data, monthly booking sheets plus monthly ingreso/egreso sheets
- PowerPoint (.pptx) — pitch decks, strictly branded
- PDF — minutas in branded format
- Gastronomic partners: Kleyopatra, El Nacional, La Casona
