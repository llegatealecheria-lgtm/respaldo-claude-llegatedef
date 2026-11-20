# Demanda, rotación y poder comercial

Esta capa es lo que convierte un benchmark de precios en revenue management. Sin
ella solo se sabe si un precio *parece* alto; con ella se sabe si el mercado lo
*acepta*.

## Las dos bases de clientes

### `Base de datos llegate 2026 (Responses)` — reservas confirmadas

Es la fuente autoritativa de demanda. Cada fila es una reserva concretada.
Cobertura verificada: **121 reservas, enero a julio de 2026**.

Columnas útiles:

| Columna | Uso |
|---|---|
| `Fecha de ingreso` | Ubica la reserva en el calendario de temporadas |
| `Propiedad adquirida` | Conjunto. **Ojo: no identifica la unidad exacta** |
| `Propietario de la propiedad alquilada` | Permite bajar a nivel de propietario |
| `Cantidad de personas` | Tamaño real del grupo. Vale oro para tarifar |
| `Motivo` | Segmento de demanda real |
| `Tipo de cliente` | Nuevo / Recurrente / Fidelizado |
| `Red social` | Canal de origen |
| `Ciudad` | Mercado emisor |

**Limitación importante que hay que declarar siempre:** la base registra el
conjunto, no la unidad. Cuando un propietario tiene varias unidades en el mismo
conjunto (Ana Karina en Doral Beach, por ejemplo), no se puede saber cuál de
ellas se alquiló. En esos casos, atribuye las reservas al conjunto y dilo
explícitamente en vez de repartirlas por suposición.

Tampoco registra número de noches ni monto cobrado. Por eso se cuenta
**reservas**, no ocupación en noches ni ingresos. Decir "ocupación del 60%"
sería inventar.

La columna `Motivo` viene en texto libre y está muy desordenada (aparecen
"Vacacional", "Vacaciones", "Vacacionar", "Vacacionala"). Normaliza antes de
agrupar.

### `Base de datos llegate 2025 (Responses)` — embudo de leads

Es otra cosa: son **contactos**, no reservas. 305 filas, la mayoría sin
propiedad asignada, con una columna `Status` (Alquilados / Seguimiento / Sin
respuesta / Cancelaron).

Sirve para tasa de conversión, no para demanda por propiedad. De las filas con
status registrado, alrededor de una cuarta parte terminó en alquiler. No mezcles
esta base con la de 2026: cuentan cosas distintas y sumarlas produce basura.

## Cómo medir rotación

Cuenta reservas por conjunto en el período disponible y compáralas contra el
resto de la cartera del mismo tamaño y segmento. No hay meta absoluta de
reservas: lo que importa es la posición relativa.

Referencia del período enero-julio 2026, unidades del foco:

| Conjunto | Reservas | Grupo promedio | Grupo máximo |
|---|---|---|---|
| Doral Beach | 25 | 6,8 | 15 |
| Thai | 24 | 5,2 | 14 |
| Costa Guaica | 14 | 6,3 | 10 |
| Guaica Suites | 6 | 3,3 | 4 |
| Villa Sol | 6 | 5,3 | 7 |
| Vientos del Mar | 5 | 3,6 | 5 |
| Playa Mar | 4 | 5,0 | 6 |
| Plaza Guaica | 3 | 5,7 | 6 |
| Tepuy | 3 | 3,0 | 4 |
| Puerto Morro | 2 | 9,5 | 10 |
| Guaicamar | 1 | 6,0 | 6 |

Criterio práctico de clasificación:

- **Rota bien** — está en el tercio superior de su categoría de tamaño.
- **Rotación media** — zona intermedia. No es alarma, pero tampoco respaldo para
  subir precio.
- **No rota** — tercio inferior, y especialmente cuando otras unidades
  comparables del mismo tamaño rotan mucho más.

Ajusta siempre por antigüedad en la cartera. Una propiedad incorporada en mayo
no puede compararse contra una que estuvo disponible desde enero. Si no se sabe
cuándo entró, pregúntalo antes de clasificar.

## Poder comercial

Cuando una propiedad cobra por encima del mercado **y aun así rota**, tiene
poder comercial: hay algo que justifica la prima. Identificarlo importa porque
es replicable y porque impide bajar precios innecesariamente.

Fuentes para explicarlo: los campos `Plus`, `Servicios` y `Puntos Criticos` del
Inventario maestro, y los atributos cualitativos de Notion.

Suelen sostener prima: salida directa a la playa, vista al mar, muelle privado,
aire central, propiedad a estrenar, ubicación céntrica, capacidad para grupos
grandes que la competencia no puede alojar.

Suelen destruirla: sin ascensor, áreas comunes deterioradas, sin piscina, poca
modernidad, ubicación poco céntrica.

Cuando una propiedad cobra por encima del mercado y **no** rota, revisa si
acumula varios destructores de prima. Ese es el argumento concreto para la
negociación con el propietario: no es que su apartamento sea malo, es que el
mercado no paga esa prima por un producto con esas limitaciones.

## Segmentos de demanda reales

Del análisis de motivos de 2026, la demanda se agrupa así:

**Vacacional** — la gran mayoría. Grupos de 4 a 6 personas. Es el negocio base.

**Eventos y celebraciones** — cumpleaños, graduaciones, eventos deportivos, de
danza y de robótica. Fechas concentradas, grupos medianos a grandes.

**Corporativo y profesional** — congresos médicos, conferencias, trabajo,
hospedaje laboral, hospedaje mensual. Volumen bajo pero estadías más largas y
menos sensibles al precio por noche.

**Diligencias y paso** — estadías cortas, grupos pequeños, muy sensibles al
precio.

Dato estructural clave: **la demanda se concentra en grupos de 4 a 6 personas.**
De 121 reservas, 76 caen en ese rango; solo 14 son de 8 personas o más.

Esto tiene una consecuencia directa para las unidades grandes: compiten por una
porción pequeña de la demanda. Antes de recomendar bajar el precio de una unidad
de 8-10 pax, evalúa si conviene tarifarla por tramos para capturar grupos de 4 a
6 (ver la sección de cotización escalonada en `comparabilidad-y-ajustes.md`).

## Señales de alerta que no son de precio

Estas aparecen al mirar la base de clientes y no se arreglan con tarifa. Cuando
las detectes, dilo, pero no las conviertas en el tema del análisis salvo que
Naylu lo pida.

**Retención baja** — de 121 reservas de 2026, 114 son clientes nuevos, 6
recurrentes y 1 fidelizado. Un problema de recompra puede costar más que
cualquier ajuste de tarifa.

**Concentración por propietario** — Ana Karina concentra alrededor de una cuarta
parte de las reservas. Es dependencia operativa, no un problema de precio, pero
condiciona cualquier negociación con ella.

**Canales** — Instagram y TikTok dominan, con una porción relevante de
referidos. Si una propiedad no rota, verifica si tuvo exposición real en esos
canales antes de concluir que el precio está mal.
