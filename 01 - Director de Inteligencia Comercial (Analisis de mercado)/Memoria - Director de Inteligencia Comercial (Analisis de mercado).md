# Director de Inteligencia Comercial de Llégate (Análisis de mercado) — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Proyecto de pricing y negociación con propietarios de Llégate a Lechería.

Estado del proyecto al exportar:
- Instrucciones: vacías
- Archivos de contexto: 33 (no descargables desde Claude, ver README)

---

## Metodología de análisis

- Reservation attribution must be unit-level, not conjunto-level
- The monthly Ingresos sheets only record the complex name — unit-level attribution for ambiguous buildings (especially Guaica Suites, Doral Beach, Thai) must come from Identificacion_Unidades_Ingresos_2026_FINAL.xlsx using the ID column
- Attributing by conjunto causes critical errors (e.g., assigning Ana Karina's reservations to Joes or another owner in the same building)
- The two income sources will never match by count: the client database counts reservations; Ingresos_Llegate counts billing events (always higher, includes referrals, split payments, extended stays)
- These two counts must never be cited as if from the same count; rotation comes from the client base, income comes from a cross-reference join by client + check-in date
- Airbnb comparables require a 15.5% host commission adjustment: the net to the host (published price × 0.845) is what competes against the owner's costo base — never the gross published price
- Airbnb is eliminating the split-fee model (effective ~September–October 2026), making 15.5% the universal standard going forward
- Benchmark data must never be hardcoded in skill files — all counts and figures must be re-derived from live source files at analysis time
- Success cases must be unit-level validated
- The validated internal success case is Alexis Márquez (Thai, known as Thai/Alexis) — validated via cross-reference
- David Hernández (Guaica Suites) is explicitly disqualified as a success case because he charges the same price as Maria Francia
- Ana Karina's Thai units involve a third-party intermediary with an embedded per-night fee — Naylu negotiates with the intermediary, not the owners directly
- Benchmark divergence rule: when comparables within a complex diverge more than 30% in price per person, no price verdict is issued — the analysis shifts to rotation; Puerto Morro is the documented case
- High-season data requires mandatory verification: confirm that the high-season costo base actually exceeds the low-season costo base before reasoning with it (documented with Balbina's units)
- Opening arguments anchor to current market comparables, never to what the owner accepted in the past
- The occupancy argument is mandatory when rotation data is weak: lowering price costs nothing on nights that would have gone vacant
- Persuasion through evidence only — no manipulative framing

---

## Forma de trabajo

### Entregables y proceso
- Paired deliverables: every owner negotiation produces an external HTML report plus an internal Markdown strategy guide
- The HTML is never generated until Naylu approves a summary of findings — a mandatory pause before writing HTML
- Document scope discipline: targeted, punctual edits to existing documents are preferred — not rewrites
- Losing visual or data elements (range graphics, bar charts, detailed comparable tables) is a critical error
- Owner profile updates happen after three or four conversations, not after each one
- Onboarding de propietarios nuevos: no usan secuencia de mensajes; envían por WhatsApp el texto de términos y condiciones (respuesta "ACEPTO") junto con el PDF "Propuesta propietarios"
- The validation log's most important column is the exact phrase used — not whether the owner accepted
- Correction-forward working style: Naylu flags errors immediately and expects implementation without re-explanation; she catches data skew and expects methodology to be stated explicitly, distinguishing exact data from derived estimates

### Arquetipos de propietario
- Six owner archetypes drive negotiation strategy: Inversionista de Portafolio Rígido, Representante de Propietario Ausente (Proxy), Delegador Familiar, Controlador/Experto Autopercibido, Optimista Estacional, Propietario Nuevo/No Materializado
- Archetypes mix three axes (who decides, how they price, tenure), so primary + secondary trait combinations are valid
- Language rules and objection scripts are tailored per archetype

### Formato
- Markdown for internal/context-loading files; HTML for human-facing deliverables
- Formal usted Spanish for all owner-facing documents
- Compact, digestible documents over exhaustive ones
- Brand palette: teal #65BBB0, gold #FFC66E, cream #F2E5B3, navy/petrol #00607F

### Archivos fuente internos (autoritativos)
- `Inventario_maestro_usado_por_Jera_IA` — sole authoritative source for pricing data
- `Benchmark_Llegate_Unidades_y_Precios` (sheet "Base (espejo Notion)", header row 4, matching via the "Comparable con:" column)
- `Identificacion_Unidades_Ingresos_2026_FINAL.xlsx` (sheet "Ingresos 2026 — Identificado") — unit-level attribution source
- `Ingresos_Llegate_9.xlsx` — billing records (counts payments, not reservations)
- `_Base_de_datos_llegate_2026` — reservation records (counts reservations, not payments)
- `Manual_Costos_Llegate.md` — cost terminology, margins, ceiling formula, per-unit reference table
- `Ficha_Propietario_Negociacion_Llegate_IA.xlsx` — 11 owner profiles with archetype synthesis
- `Avatar_Propietario_Llegate_UNIFICADO` — owner archetype reference

### Herramientas y datos externos
- Skill: `analista-de-mercado-llegate` — a multi-file skill package with references for comparability/adjustments, demand/rotation, pricing/seasons, and focus portfolio
- AirDNA (free tier, submarket code 85291, labeled "Anzoátegui" but geographically Lechería); median ADRs: 1BR ~$41.50, 2BR ~$57.50, 3BR ~$62.50 — directional reference only
- AirDNA occupancy rate is locked behind the paid plan; an "Ocupación Implícita" estimate can be derived from ADR and annual income figures
- PDF generation via wkhtmltopdf; reliable vertical mobile-format pattern: `--page-width 100mm --page-height 200mm` with zero margins, `--disable-smart-shrinking`, `--zoom 0.52`, CSS `page-break-after:always` on every section
- Logo embedded as base64 to prevent asset loading failures; image verification via `pdftoppm -png -r 90`
- Notion connected via MCP (workspace llegatealecheria@gmail.com); Cartera de Propiedades database ID `367eb89c-87eb-8043-8920-cbe07a479caf`
- Notion formula/rollup columns are not accessible via query — they require per-page fetch or export
- Documenta los formatos de Llégate en Notion, página "Formatos of LAL" → base "Glosario de formatos" (plantilla por entrada: Ficha · Info de interés · Paso a paso)
- El avatar de propietarios, los arquetipos y la bitácora de validación viven ahora en el Google Sheet "AVATAR Y BITÁCORA DE VALIDACIÓN"
- Para propietarios nuevos o por captar: dos informes separados, uno de recomendaciones de mejora del apto y otro de precios (tarifa de aliado comercial distinta a la del cliente directo, temporada baja/alta, semana, 15 días, mes) con la propuesta de anfitrionaje; la evidencia de mercado sigue el modelo del informe de Balbina, con enlaces clicables y fotos de la competencia; los enlaces de Airbnb se validan con Naylu antes de ponerlos en el informe
- Informes de precios a propietarios siempre en euros; ella misma captura las fotos de la competencia y Claude se las va solicitando
- Antes de fijar tarifas de un propietario, preguntarle siempre cuánto le quiere ganar a la propiedad (con sugerencia interna de margen); regla fija: el propietario siempre debe dar precio de aliado
- Cotizar propiedades nuevas partiendo del historial de tarifas de aliado del estándar corporativo (carpeta de propuestas de estadías largas), alineando características similares del inmueble (ej. Costa Guaica de Argenis como referencia para Katiuska); el precio del checklist de propiedades es el costo de aliado del propietario
- Diseño preferido: el del informe de Balbina (no el de Luz León); tarifa de anfitrionaje estándar 15 € por reserva, sin tarifa preferencial tachada ni bloque de "Término"

---

## Área: Captación de propietarios (dic 2026 – ene 2027)

- Contenido y ads para captar propietarios nuevos por falta de inventario en diciembre y enero; los guiones se desarrollan en el proyecto de comunicaciones
- Condiciones para propietarios nuevos: dispuestos a ajustar precios, a escuchar análisis de mercado y a que Llégate les anfitrione la propiedad en diciembre
- Beneficios que se comunican: alquilar más, subir ocupación y delegar atención al cliente y anfitrionaje
- En la publicidad no se habla de precio ni de análisis de mercado (eso va en el onboarding); no abrir siempre con dinero; Llégate no garantiza el 100% de las ventas, sí un volumen estimado
- Requisitos de propiedades: buen estado, modernas, sin filtraciones, sábanas estándar hotelero; propietarios atentos y dispuestos a mejorar
- Más de 500 clientes interesados perdidos en diciembre y enero por falta de apartamentos; fecha límite de entrada: noviembre
- No usar testimonios de propietarios con nombre sin su permiso

---

## Área: Catálogo corporativo

- Catálogo para empresas de corporate stay, inspirado en el de Guaica Suites (tono elegante/informativo); el de Thai se descartó por tono muy turístico
- 11 unidades candidatas: Guaica Suites 423 (David), Guaicamar B1-21 (Balbina), Guaicamar J113 (Jair), Solmar 902 (Andreina), Victoria Park (Gabriela), Thai K-PB5 (Dalcira), Thai C-PH8 (Alexis), Guaicamar E1-14 (Isidra), Costa Guaica (Argenis), Plaza Guaica 3-6-1 (Johanna), Entremares Torre G (Yuliditza)
- Solo 3 pasan la certificación sin pendientes: Guaica Suites 423, Guaicamar B1-21, Guaicamar J113; se incluyen las 11 agrupadas por estado (disponible ahora / en certificación)
- Mínimo corporativo: 3 noches. Escalones: 3-6 noches tarifa estándar, 7-29 noches tarifa corporativa con descuento (sin definir), 30+ a cotizar
- Ninguna propiedad tiene planta eléctrica de respaldo
- La política de cancelación turística no se traslada tal cual a corporativo (pendiente)
- Pendientes: factura fiscal, kit ejecutivo (contenido y precio), protocolo de incidencia/SLA de respuesta, contacto para el catálogo

---

## Área: Estadías largas

- Para 30+ noches, la comisión de Llégate puede ser de $10 por noche
- Se usa el formato de precios de Alquila en Lechería (precio por noche por tramo: noches cortas, 1 semana, 15 días, 1 mes), no el Excel de costos de ventas
- Cálculos de estadías largas sin IVA
- Descuentos por estadía de 6+, 10+ y 15+ noches, empezando por las unidades del catálogo corporativo
- Promoción opcional entre semana: descuento de $10 o $15 por noche de lunes a jueves, asumido 100% por el propietario; se descartó la promoción de fidelidad
- PDF de propuesta de estadías largas: uno por propietario más un maestro interno; en la tabla de mercado no nombrar Hostaway ni el hotel de estadía extendida
- Guaicamar B1-21: tramo de 10 a 14 noches, mes sin cambio; precio por personas (4 pax $50, 6 pax $65, 8 pax $85)
- Comisión por tramo: unidades chicas (Victoria Park, Solmar 902, Esmeralda 402, Guaica Suites 423) $15 de 3 noches a la semana, $12 a 15 noches, $10 al mes; unidades grandes de más de 2 habitaciones (Guaicamar, Costa Guaica) siguen en $20
- En estadías de 3 a 6 noches el precio baja $5 en todas las unidades; en la promo entre semana Llégate cobra una comisión mínima que no se muestra al propietario
- El cuadro de reservas, noches y ocupación solo se muestra en Costa Guaica y Guaicamar; la ocupación la calcula Claude
- Costa Guaica (Argenis) completo; Guaicamar B1-21 pendiente de actualizar
- PDF adicional para Yuliditza Goitia (Entremares Torre G, Grupo B en certificación)

---

## Área: Negociación Maria Francia (Guaica Suites 131)

- Primera negociación con la propietaria Maria Francia
- Costo actual en Guaica Suites 131 (1 hab, cap. 5): $55/noche; objetivo: bajarlo a $45/noche
- Tiene otra unidad en Solmar (fuera de esta negociación)
