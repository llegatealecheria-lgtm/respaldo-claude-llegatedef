# Manual de costos y precio mayorista — Llégate a Lechería

Documento de referencia interna. v2.0 · Julio 2026.
Se lee antes de analizar cualquier precio o preparar una negociación.

---

## 1. Diccionario de costos

Columnas del archivo *Inventario maestro usado por Jera IA*.

| Columna | Qué es | De quién |
|---|---|---|
| Costo base propiedad | Lo que el propietario exige por noche | **Propietario** |
| Costo base escalonado | Igual, pero distinto según cuántas personas entren. Se lee `5=75` = $75 si van 5 | **Propietario** |
| Incremento por persona | Cuánto suma el propietario por persona extra | **Propietario** |
| Incremento por Temporada Alta | Cuánto sube el propietario en alta | **Propietario** |
| Costo base propiedad Temporada Alta | Lo que exige el propietario en alta | **Propietario** |
| Costo Real Temporada Baja / Media / Alta | Lo que Llégate le cobra al huésped = costo base + margen | **Llégate** |
| Limpieza | Se cobra aparte, encima de la tarifa por noche | **Propietario** |
| Depósito | Garantía reembolsable, no es ingreso de nadie | — |

**REGLA DE ORO:** para saber si un propietario está caro o barato se usa **Costo base**. Nunca Costo real — ese ya tiene el margen adentro y da un resultado falso.

---

## 2. Margen actual de Llégate

Es un monto fijo por noche, no un porcentaje. Verificado en las 36 unidades:

| Temporada | Margen | Cobertura |
|---|---|---|
| Baja | +$20 | 33 de 36 unidades (1 con $15, 2 con $25) |
| Media | +$25 | Las 36, sin excepción |
| Alta | +$20 / +$25 / +$30 | Disparejo: 19 / 5 / 12 unidades |

En este documento se usa **+$20** como referencia. Actualizar cuando se apruebe el esquema por porcentaje según capacidad.

---

## 3. Cómo comparar contra el mercado

- Los precios del benchmark son lo que la competencia le cobra **al huésped**.
- **Airbnb se queda con 15,5%.** Publicado en $70 → al anfitrión le quedan ~$59. Ese es el número que compite contra el costo base.
- **Mercado Libre no cobra comisión** al anfitrión. Se usa tal cual.
- **Ajustar por capacidad:** sacar precio por persona del comparable y multiplicar por la capacidad de nuestra unidad. No comparar un 4 pax contra un 8 pax.

---

## 4. El techo del propietario

**Techo = precio de mercado del conjunto − margen de Llégate ($20)**

Es el máximo que el propietario puede pedir para que su unidad salga publicada al precio de mercado.

Ejemplo: Thai, 4 personas, mercado $58. Techo = 58 − 20 = **$38**.

> Cuánto se acepta por encima del techo queda a criterio de Naylu, caso por caso. No hay una regla fija.

---

## 5. Tabla de referencia (benchmark julio 2026, margen $20)

| Propietario | Unidad | Pax | Mercado | Techo | Pide | Ajuste |
|---|---|---|---|---|---|---|
| Balbina | Guaicamar | 8 | $96 | **$76** | $95 | bajar $19 |
| Balbina | Mar de Leva 8-6 | 5 | $62 | **$42** | $75 | bajar $33 |
| Balbina | Mar de Leva 7-4 | 6 | $75 | **$55** | $65 | bajar $10 |
| Ana Karina | Thai B/N1-8 | 4 | $58 | **$38** | $90 | bajar $52 |
| Ana Karina | Thai D-PH2 | 4 | $58 | **$38** | $90 | bajar $52 |
| Ana Karina | Thai N/PB-01 | 4 | $58 | **$38** | $90 | bajar $52 |
| Ana Karina | Doral N824 | 6 | $66 | **$46** | $80 | bajar $34 |
| Ana Karina | Doral N11 | 4 | $44 | **$24** | $60 | bajar $36 |
| Ana Karina | Doral K-PB3 | 5 | $55 | **$35** | $50 | bajar $15 |
| Dalcira | Thai K-PB5 | 4 | $58 | **$38** | $55 | bajar $17 |
| Joes | Doral 811 | 4 | $44 | **$24** | $60 | bajar $36 |
| Virginia | Playa Mar 4B4 | 4 | $50 | **$30** | $60 | bajar $30 |
| Simon | Villasol A-109 | 4 | $53 | **$33** | $60 | bajar $27 |
| Argenis | Costa Guaica T1/N2 | 5 | $52 | **$32** | $75 | bajar $43 |
| Maria Francia | Guaica Suites 131 | 5 | $62 | **$42** | $50 | bajar $8 |
| Maria Francia | Solmar 802 | 3 | — | — | $50 | sin comparable |
| Joanna | Plaza Guaica 3-6-1 | 4 | $47 | **$27** | $50 | bajar $23 |
| Alexis | Thai C-PH8 | 5 | $73 | **$53** | $60 | bajar $7 |

Solmar no tiene comparable cargado en el benchmark. Levantarlo antes de negociar.

---

## 6. El precio mayorista

Muchos propietarios nos dan **el mismo precio que le darían a un cliente que llega solo**. Al sumarle el margen, el resultado se sale del mercado.

La propuesta: que el propietario maneje dos precios.

| | Precio al público | Precio para intermediarios |
|---|---|---|
| A quién | Al cliente que le escribe directo | A Llégate |
| Quién trabaja | Él: atiende, filtra, cobra, coordina, asume el riesgo | Nosotros. Él solo recibe |
| Nivel | Su precio normal, nadie le pide cambiarlo | Más bajo, compensado por volumen |

---

## 7. Qué gana el propietario a cambio

### A) Se ahorra todo el trabajo
Responder mensajes a cualquier hora, filtrar quién entra a su apartamento, coordinar llegadas y salidas, resolver problemas durante la estadía. Trabajo real que no hace ni paga.

### B) Es un aliado comercial, no un cliente suelto
No le llevamos una reserva y desaparecemos. Gestionamos su unidad de forma continua todo el año.

### C) Baja el precio, sube la ocupación, gana más
**Este es el argumento más fuerte y hay que usarlo con números.**

La lógica: bajar $10 por noche no cuesta $10. Cuesta $10 **solo en las noches que ya se iban a vender**. En las noches que hoy quedan vacías, ese ajuste es la diferencia entre cobrar algo y no cobrar nada.

Cuenta ejemplo:

| Escenario | Precio | Noches vendidas al mes | Ingreso |
|---|---|---|---|
| Hoy | $60 | 4 | $240 |
| Ajustado | $45 | 8 | **$360** |

Bajó $15 por noche y ganó $120 más al mes.

**Datos reales que respaldan esto** (enero–julio 2026, 156 reservas confirmadas):

| Conjunto | Reservas | Noches |
|---|---|---|
| Doral Beach | 35 | 90 |
| Thai | 29 | 62 |
| Costa Guaica | 15 | 46 |
| Coral Suites | 7 | 18 |
| Playa Mar | 6 | 19 |
| Villasol | 6 | 14 |
| Guaica Suites | 6 | 14 |
| Guaicamar | 4 | 35 |

Los conjuntos con más rotación son los que están mejor posicionados en precio. La demanda existe: se concentra donde el precio permite competir.

**Cómo decírselo:** no "bájame el precio", sino "tu apartamento se está alquilando X noches al mes; a este precio se alquilaría más, y aunque cobres menos por noche terminas recibiendo más al mes".

---

## 8. Guion de la conversación

**Paso 1 — Abrir con el mercado, no con la rebaja.**
> «Estuve revisando lo que se está publicando en tu mismo conjunto para agosto, en unidades de la misma capacidad. Quiero que lo veas.»

**Paso 2 — Separar los dos precios.**
> «No te estoy pidiendo que bajes tu precio. Tu precio al público sigue siendo el tuyo. Lo que te propongo es un precio distinto para nosotros, como haría cualquier proveedor con un canal de venta.»

**Paso 3 — Nombrar lo que recibe: trabajo ahorrado + más ocupación.**
> «Con nosotros no atiendes mensajes, ni filtras quién entra, ni resuelves nada durante la estadía. Y no somos un cliente que aparece una vez: trabajamos tu apartamento todo el año.»
> «Tu apartamento se alquiló X noches este mes. A este precio se alquilaría más, y aunque cobres menos por noche, al final del mes recibes más.»

**Paso 4 — Cerrar con el número exacto** de la tabla del punto 5. Nunca dejar la conversación abierta.

---

## 9. Pendientes

- Definir los porcentajes de margen por categoría de capacidad (Pequeños 3–4, Estándar 5–6, Grandes 8–10) y por temporada. Mientras tanto se usa +$20.
- Decidir en qué categoría entran las unidades de 7 pax (Virginia, Andrea Rinaldi).
- Definir dónde vive el checklist "Usa precio TA". Hoy no está en el Inventario maestro.
- Decidir si el precio mayorista es igual todo el año o si en alta se pide más cesión por volumen.
- Levantar comparables de Solmar.
- **Anomalía Balbina:** sus tres unidades tienen incremento de temporada alta de $20, pero su costo base de temporada alta es igual o menor al de temporada baja (Guaicamar $95→$90; Mar de Leva 8-6 $75→$70; 7-4 $65→$65). Confirmar si es error de carga.
