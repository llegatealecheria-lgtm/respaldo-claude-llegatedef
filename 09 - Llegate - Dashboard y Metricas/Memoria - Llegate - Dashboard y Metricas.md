# Llégate a Lechería — Dashboard / Métricas — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Dashboard gerencial en React conectado al CRM de Notion, más el reporte del Forms de clientela.

---

## Propósito
- Live, interactive CRM dashboard (React/JSX) pulling data from four Notion databases: KPIs, funnel charts and property performance
- Managerial control panel for the rental operation

## Paleta (exacta, confirmada)
- Teal (dominante): Pantone 563C → `#6BBBAE`
- Crema (dominante): Pantone 7499C → `#F1E6B2`
- Dorado/mostaza: Pantone 1355C → `#FFC66E` (no #C9A24B ni #FFC56E)
- Azul marino: Pantone 7707C → `#00617F`

## Identidad del dashboard
- h1: "Dashboard Llégate a Lechería"
- Label above h1: "Panel Gerencial"
- Logo: original circular brand mark (sol + olas + wordmark), embedded as base64 PNG with white background removed
- Never recreate or redesign the logo as SVG

## Fuentes de datos (IDs de Notion)
- Clientes: `1fa608e7-2324-4d0e-8ce5-d6badd1cda45`
- Pipeline Comercial: `fdf17c5c-615c-4dab-80e8-b0d73ac58cff`
- Reservas: `98108515-533c-458c-b2e0-3dbe27d272fd`
- Cartera de Propiedades: `367eb89c-87eb-8018-beee-000b92fb67a0`
- Página Dashboard Comercial: `379eb89c-87eb-80cf-8333-d8ae177eb420`

Campos por base:
- Clientes: Edad, Ciudad de origen, Fecha primer contacto
- Pipeline: Motivo de viaje, N.º de huéspedes, Propiedad de interés (relación), Escalado a humano, Motivo de escalamiento
- Propiedades: Target, VIP

## Estado — vistas y tarjetas
- `crm-dashboard.jsx`: React artifact with Recharts, connected live to Notion via the Anthropic API's MCP server
- KPIs including "Total de Leads" and "Recurrencias activas"
- Funnel, donut, bar and revenue line charts
- "Rendimiento de Propiedades": three lines (Enviadas, Reservadas, Recurrencias) plus a local size filter (Pequeña/Mediana/Grande) for that chart only
- Casos Escalados a Humano (by motivo)
- Motivo de viaje
- Tamaño promedio de grupo — avg N.º de huéspedes across pipeline entries in the period
- Clientes por Ciudad de Origen
- Clientes por Rango de Edad: 18-25 / 26-35 / 36-45 / 46-55 / 56+
- Reservas del período por segmento (Target) + ingresos de propiedades VIP
- Age filter buckets in the filter UI: 20-25 to 60-65

## Filtro de período global
- Pills in header: Todo / Día / Semana / Mes / Trimestre / Semestre / Año, default "Todo"
- Clientes → "Fecha primer contacto"; Pipeline → "Fecha creación"; Reservas → "Fecha reserva"
- Not filtered by period: seguimientos vencidos, próximos check-ins, "Nivel de rotación"

## Estilo visual
- Airy, rounded, minimalist sidebar, blob accents, alternating teal-pale/cream-pale sections
- Radii: cards ~28px, sections ~40px
- Gradient pill-shaped bars; rounder KPI badges
- Rendimiento de Propiedades: teal-pale = Enviadas, gold = Reservas, navy = Recurrencias

## Actualización y caché
- No visible "Actualizar datos" button by design
- The ✨ icon at the top of the sidebar silently triggers a Notion refresh
- `window.storage` caches the last Notion pull so it paints instantly, then re-syncs in the background

## Próximos pasos
- Possible deployment to Vercel for a permanent URL — offered, not confirmed
- `crm-dashboard.jsx` doesn't persist between conversations; it must be re-uploaded each session

---

## Aprendizajes técnicos

### API y MCP
- `max_tokens` must be 8192 for Notion queries (4096 before; 1000 caused silent JSON truncation)
- Four simultaneous API calls hit `exceeded_limit`; use pairs of 2 via `Promise.all`
- Retry on `exceeded_limit` or 429 up to 3 times with backoff (`attempt × 1200ms`)
- Always show the real `error.message` in the UI
- Notion MCP prompts must request minified JSON array only — no markdown, fences or prose
- View filter/sort configs via `notion-fetch` on `https://app.notion.so/p/[view-id]`

### Nombres de campos (crítico)
- Relation field is "Recurrencias" (Clientes) / "Recurrencias asociadas" (Propiedades) — NOT "Oportunidades"
- JSON key `totalRecurrencias`
- "Total Enviadas" rollup is never fetched; "enviadas" is recomputed client-side from Pipeline entries at "Opciones Enviadas" or later
- Rollup-of-formula fields are unreliable via MCP — always recompute client-side
- Property size is parsed from the title pattern `(Tamaño)` — no separate field

### Forma de trabajo
- Spanish with natural technical vocabulary ("pills", "artifact", "degradado", "radios", Recharts names)
- Iterative rounds with visual evaluation
- Client-side recomputation preferred over Notion rollups/formulas
- Visual references (images, designs like "Donezo") guide aesthetics
- Validate JSX with Babel (`@babel/core`, `@babel/preset-react`, `@babel/preset-env`) before delivery

### Herramientas
- React (JSX) + Recharts; Notion as backend; Anthropic API MCP server; Babel; Vercel (pending)
- Property queries: `Notion:notion-search` with `collection://367eb89c-87eb-8018-beee-000b92fb67a0`

---

## Área: Reporte del Forms de clientela

### Propósito y alcance
- Reporte desde el Sheet de respuestas del Forms de clientela; fuente "_Base_de_datos_llegate_2026__Responses_.xlsx" (hoja "Form Responses 1", ~201-202 filas)
- No reemplaza al dashboard de Notion — es para reportes puntuales
- Sin conexión en vivo: se regenera cada vez que se comparte una versión nueva del Sheet
- Artifact publicado: https://claude.ai/artifact/GMm3nnzhdXiEvZumSjs2BH (sí persiste entre sesiones)

### Filtro de período
- Basado en "Fecha de ingreso" (check-in), no en el Timestamp del formulario
- Permite elegir instancias específicas en todas las granularidades (Día/Semana/Mes/Trimestre/Semestre/Año)
- Cobertura del snapshot: ene-sep 2026

### Limpieza de datos
- Motivo de viaje: variantes de "vacacional" → "Vacacional"; "15 años" (Jennifer Sulbaran, grupo de 16) → "Cumpleaños"
- Rango de edad: 20-25/26-35/36-45/46-55 y último rango "60+"; rangos declarados se ubican por punto medio; edades <15 → "Sin dato"
- Ciudad: variantes de "no se obtuvo" → "Sin dato"
- Canal: "Referido por cliente X" → "Referido"
- "Cantidad de personas": si menciona mascota, se extrae el número de personas y se marca aparte
- Descartadas por bajo llenado: "Nombre de evento" (1%) e "Identificador de propiedad" (0%); "ID de propiedad alquilada" fuera por ahora; "Cantidad de noches" incluida (~35% de llenado) con nota

### Propietarios (ranking de unidad más alquilada)
- Se agrupa por "Conjunto — Propietario"
- Fusiones: Alexis/Alexis Marques/Marquez/Márquez → Alexis Márquez (Thai); Joanna/Joanna Salazar → Joanna Salazar (Plaza Guaica); Virginia/Virginia (Playa Mar) → Virginia (Playa Mar); Andreina Kovacic/Kovavic → Andreina Kovacic (Solmar)
- "Alejandro" (Yate o Lancha) es Alejandro Rodríguez, el capitán; Yate/Lancha/Yate o Lancha unificados (mismo bote)
- "Ashly Contreas o Andrea Rinaldi" se deja como propietario conjunto
- "Alquila en lecheria" es aliado comercial, se deja tal cual

### Identidad visual
- Misma paleta del dashboard; dorado #FFC66E; bordes de tarjeta más marcados
- Logo con aro blanco

### Métricas
- Motivo de viaje con chip de más/menos frecuente
- Rango de edad, tipo de cliente, ciudad de origen y canal, filtrables por período
- Tamaño de grupo: promedio + distribución (1-2/3-4/5-6/7-8/9-12/13+)
- Grupos con mascota
- Unidad más alquilada (Conjunto — Propietario)
- Resumen dinámico del período con tendencias y puntos de mejora

### Interactividad
- Tooltips en barras y segmentos
- Motivo de viaje, Unidad y Tipo de cliente filtran todo el reporte, con chip para quitar el filtro
- KPIs animados al cargar; transición suave al cambiar de período

### Aprendizajes técnicos
- No usar librerías de gráficos por CDN — Chart.js falló en el artifact publicado; gráficas en SVG inline a mano
- El logo se extrae siempre por código (recorte + base64 con Python), nunca transcribiendo base64 a mano
