# Gestión con propietarios — Memoria del proyecto

Respaldo exportado el 20 nov 2026. Operación de Llégate a Lechería con los propietarios: informes, comunicación y anfitrionaje.

---

## Principios
- Never invent data — consult before assuming; never fabricate figures, owner names or amenities. "Lo que ya funciona" sections are built only from photo-verifiable details
- Owner communication: issues framed as improvements that protect portfolio standing, not disqualifying problems (e.g. "humidity stains" instead of "mold" in the Bahía Redonda report)
- Property reports frame issues as improvements to maintain portfolio standards, not barriers to publication

## Estilo de comunicación
- Business communications (especially conflict or negotiation): strategically structured, emotionally intelligent, persuasive — assertive without losing professionalism, anchored in documented facts
- WhatsApp-casual but strategically structured for owners/partners; formal style for contracts and proposals

## Flujo de trabajo
- Activates custom skills (`/consultor-calidad-propiedades-llegate`, `/director`) for recurring workflows
- Iterates with mid-course corrections; flags inconsistencies, math errors or tone issues proactively

## Marca
- Palette: teal `#65BBB0`, navy `#00607F`, gold `#FFC66E`, cream `#F2E5B3`, Poppins font

## Herramientas y notas técnicas
- PDF: `wkhtmltopdf --enable-local-file-access --page-size Letter --margin-top 0 --margin-bottom 0 --margin-left 0 --margin-right 0`; images as base64 data URIs
- HEIC images need `pillow-heif` with `pillow_heif.register_heif_opener()`; portrait images need `max-height` (e.g. 300px) to avoid page bloat
- Photo rows: `.figcaption` with `max-width: 170px; margin: auto`, `.figrow` with `gap: 28px`; single photos `max-width: 300px`
- `Ingresos_Llegate_10.xlsx` with `openpyxl`: scan rows 1–5 for the "propiedad" header; broad substring matching for property names ("guaica", "tepu"); Aug–Sep 2024 sheets record commission per night, not full rate
- PowerPoint (16:9) and Word (.docx) with Cambria/Calibri for formal documents

---

## Área: Anfitrionaje
- El anfitrionaje se presenta a los propietarios como parte obligatoria del servicio, pagado por el propietario: tarifa por reserva escalonada (10 € para 1–2 noches, 15 € para 3+ noches), solo check-in; además el huésped paga 6 € fijos por reserva, incluidos en la cotización (el check-out queda a cargo del propietario). Es la única tarifa que Llégate cobra a propietarios además de su comisión. Quiere que todos lo usen porque da más presencia de marca
- Evaluando escalonar por noches (6 € para dos noches, 10 € desde 3 noches) y que el huésped pague otros 6 € por reserva; aún sin decidir

## Área: Cierre anual 2026
- Está armando un "proyecto madre" para el cierre de todo lo realizado en el año, cargando resúmenes de sus otros proyectos (incluido este)

## Personas
- **Andrea:** anfitriona designada para el anfitrionaje; hace el check-in y entrega a los huéspedes el documento para firmar; se le paga por reserva
- **Luz León:** propietaria de un apartamento en el Conjunto Residencial Las Palmeras (Lechería). Se le está pidiendo bajar su tarifa de 55 € a 40 € por noche para que el precio publicado (con comisión) quede en 55–60 €; se le ofrece anfitrionaje (solo check-in) a tarifa preferencial de 10 € por reserva
