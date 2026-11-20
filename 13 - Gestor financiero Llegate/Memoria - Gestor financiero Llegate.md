# Gestor financiero Llégate — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Seguimiento financiero en Google Sheets/Apps Script y automatizaciones.

---

## Resumen del negocio
- Vacation and corporate rental intermediary in Venezuela; doesn't manage properties directly
- Revenue: fixed commission per night (tiered by capacity) plus fixed management fee per booking
- Earnings tracked in USD/USDT even when some charges are in other currencies
- Goal: clear weekly cash flow visibility (income vs. expenses, free cash) and monthly projections
- Jera (sales advisor) receives 20% commission on Naylu's earnings, tracked and paid weekly

## Sistemas y archivos
- Google Sheets is the primary financial platform
- Income now registered in "Producción Llegate a Lechería" (one tab per month), replacing "Ingresos Llegate"; the weekly agent should read from Producción
- From September 2026 the dashboard comes only from Producción, replacing earlier September entries
- Commission collection: usually 1 night of commission discounted at booking, the rest pending until COMPLETADO = Sí; December bookings are paid ~half upfront, flagged in red to enter the pending amount manually
- Flujos de cobro (según la nota bajo cada confirmación en WhatsApp): abono a Llégate y el resto al propietario; o todo a Llégate y ella pasa la parte del propietario; o se descuenta toda la comisión del abono. A veces el propietario paga aparte una comisión pendiente
- Nunca retiene dinero del propietario: se transfiere el mismo día
- COMPLETADO = Sí → comisión cobrada completa; No → aún le deben comisión (al propietario ya se le pagó)
- Convenciones en Producción: método "Pagado al propietario" cuando el cliente pagó directo (sin REF); REF con los 4 últimos dígitos cuando el propietario le paga a Llégate; COMISIÓN PAGADA con formato "Reserva: $X (ref) + Extra: $Y (ref)"
- Las reservas entran a Producción por automatización: la confirmación se pasa a Telegram con la comisión ganada y se registra sola
- Cancelaciones: Llégate se queda su parte del abono (una noche o el 50%) y el propietario la suya; se marca "Cancelada" en COMISIÓN PAGADA. La moneda real de las reservas es el euro
- "Dashboard_llegate_DEF" — dashboard de ingresos, egresos, ROI y colchón
- "Ingresos 2026" is a separate Excel file from "Dashboard_llegate_DEF"
- "presupuesto madre" — personal budget, separate from the business; Llégate entries in personal files are excluded
- Google Apps Script runs the weekly income automation
- Google Drive for file storage
- openpyxl notes: `copy()` for styles, `unmerge_cells()` before writing into merged zones, dual-load (`data_only=False` formulas / `data_only=True` values); validate with the recalc script
- Skill packaging: description field has a 1024-character limit
- Three non-overlapping skills: `finanzas-llegate` (cash flow, projections), `arquitecto-de-google-sheets` (structure/formulas), `analista-de-mercado-llegate` (pricing/benchmark)

## Estado — automatización financiera
- Apps Script weekly agent (v5+) registers income from "Ingresos Llegate" into "Ingresos 2026"
- Each reservation splits into "Reserva nueva" (paid now) and "Pendiente" (until check-in passes and INGRESO PENDIENTE is set to 0)
- Payment method → currency: PM → Bs; Binance/USDT → USDT; Zelle/Efectivo/Transferencia → Divisas
- Ledger with three helper columns (Clave auto, Origen auto, Tipo auto) prevents duplicates
- Unique key = normalized cliente + propiedad + fecha reserva
- Jera's commissions register as weekly totals (integer floor of her Semana column), always Pagado
- Bugs fixed through v5: timezone crash (custom `_ymd_()`), double-counting when pending clears (frozen pending amount), CONTROL COMISIONES header found by dynamic scan

## Estado — dashboard
- Fixed SUMIFS range caps and month-criteria errors in Egresos Mensuales and Dashboard
- Added August–December expense blocks
- Added "Incluir en ROI" column and ROI section
- Added "Origen del pago": Caja del mes / Colchón / Aporte personal
- Added Saldo de Colchón acumulado and Utilidad Operativa Ajustada
- Colchón starts from zero in January 2026
- Most monthly expenses are funded from the cushion, so Utilidad Operativa Ajustada and Saldo de Colchón are the central health metrics

## Estado — presupuesto personal
- Workflow: Naylu passes the updated expense file (Gastosssss) and Claude maps categories and deduplicates into the monthly master budget
- Ambiguous entries (e.g. Ahorro cumpleaños / Cashea) flagged for review
- Anomalies in the master file are surfaced, not silently deleted

## Próximos pasos
- Stabilize the Apps Script agent for weekly runs
- New monthly tabs from the August 2026 template
- Keep syncing the personal budget
- Two unresolved dashboard items: a January equipment expense with uncertain origin, and two Automatizaciones rows with swapped Mes values

---

## Área: Llégate Manager
- Sistema propio que une CRM, disponibilidad centralizada de ~40 propiedades, cotizador, reservas, finanzas, portal de propietarios e integraciones (WhatsApp, Instagram, TikTok, Google Calendar)
- Stack: Lovable + React/TypeScript + Supabase (Auth, Storage, Edge Functions, RLS); ~US$50–100/mes en herramientas
- Por fases: análisis primero, sin programar; datos ficticios y sin el WhatsApp operativo hasta aprobar pruebas
- Equipo comercial de 2–3 asesoras; Gera atiende por WhatsApp (un solo número comercial)
- Nov 2026: empezó por el módulo financiero en Lovable (prototipo); prioriza cálculos correctos y auditables
- El Sheets "Producción Llégate a Lechería" sigue como fuente de verdad y se sincroniza hacia la app (Sheets → Supabase)
- Es propietaria del Sheets "Producción" y tiene otras automatizaciones de Apps Script en ese proyecto (no borrarlas al agregar scripts nuevos)
