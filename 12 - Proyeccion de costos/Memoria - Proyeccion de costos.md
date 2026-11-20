# Proyección de costos — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Modelo de comisiones y precios de Llégate a Lechería como intermediario.

---

## Propósito
- Naylu works as an intermediary property manager for short-term rentals in Lechería
- Llégate is the middleman, not the owner, and earns a fixed net commission per night in euros (not a percentage)
- Goal: pricing and commissions attractive to owners and sustainable for Llégate
- Portfolio: 36 properties

## Propietarios
- Andreina Kovavic — Solmar (active pilot property)
- Francisco — Vientos del Mar
- David — Guaica Suites
- Isidra — Guaicamar / Balbina
- Balbina — Guaicamar Torre B N21

## Modelo rediseñado
- Moved away from a flat structure
- Rule 1 — Duration-discount curve on the owner's cost: 100% for 1 night down to ~58% for 1 month
- Rule 2 — Fixed €8 management fee per reservation, regardless of duration
- Rule 3 — Tiered nightly commission by capacity, with two seasons: Baja (absorbs Media) and Alta
- Rule 4 — Cleaning pass-through only for stays up to 4 nights; cleaning fees go to the cleaners, not Llégate income
- Commissions from €15–18 (up to 4 pax) to €25–30 (11–12 pax), depending on season
- Cross-season reservations use the commission of the starting season
- Workation/Corporate Stay is excluded from seasonality, always at base tier

## Entregables
- Three-tab Excel (Parámetros, Cartera, Cálculo) covering the 36 properties across duration tiers and both seasons — formula-driven
- Interactive HTML presentation in brand colors with scroll animations and Chart.js: rationale, the four rules and projections for three pilot properties (August–December)

## Próximos pasos
- Validate and roll out beyond the three pilots (Vientos del Mar, Guaica Suites, Guaicamar) to the whole portfolio
- Present the model to owners with the HTML presentation

## Aprendizajes y principios
- Commissions are fixed euro amounts, not percentages — fundamental to all design
- Validate concepts with concrete number examples before committing
- Simplicity: seasons collapsed from three to two to simplify cross-season calculations
- All financial outputs in euros
- Parametric, auto-recalculating model
- Pilots use real properties and realistic occupancy projections

---

## Herramientas y datos
- Master inventory in Google Drive, retrieved as CSV; file ID: 1YDvUhkQu63wJuGdxN1C-75ZzXStdcAGA2bh2qf9AL0w
- Python/pandas for processing
- Inventory CSV uses European formatting (e.g. "45,00 €") — needs custom parsing
- Commission model in .xlsx, validated with the recalc script
- Chart.js for interactive graphs in HTML
- Related skill: `analista-de-mercado-llegate`
