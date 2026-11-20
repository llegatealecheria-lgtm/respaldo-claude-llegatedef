# Estructura de precios, márgenes y temporadas

## La realidad de mercado vigente (julio 2026)

**Esta sección manda sobre la tabla teórica de márgenes que sigue abajo.**

El mercado bajó y los propietarios mantienen precios de temporada alta que ya no
se sostienen. En la práctica, Llégate está operando así:

- Margen aplicado: **$15 a $20 por noche**, en la línea entre temporada baja y
  media.
- Máximo aplicado: **$25 por noche** y solo en propiedades grandes.
- Objetivo mínimo: **$20 de margen** como norte general.

Consecuencia directa para el análisis: **las columnas `Costo Real Temporada
Alta` del Inventario maestro no representan precios cobrables hoy.** Existen en
el archivo pero el mercado no las acepta. Si construyes un análisis sobre ellas,
el resultado es ficción.

Analiza contra temporada baja y media. Menciona temporada alta solo para mostrar
la brecha entre lo que el propietario pide y lo que el mercado paga — que es
exactamente el argumento de negociación.

Esto se irá ajustando conforme los propietarios bajen. Si en la conversación
Naylu indica márgenes distintos a los de arriba, esos mandan.

## Tabla de márgenes de referencia

Es la estructura diseñada, útil como marco conceptual y como meta de
recuperación cuando el mercado se reactive. No como supuesto operativo actual.

**Apartamentos pequeños** (costo propietario 3-4 pax, $40-$50)

| Temporada | Costo | Precio al cliente | Ganancia | Margen |
|---|---|---|---|---|
| Baja | $40 | $55 | $15-$20 | 27% |
| Media | $45 | $65 | $20 | 38% |
| Alta | $50 | $75 | $25 | 44-50% |

**Apartamentos estándar** (costo propietario 5-6 pax, $60-$80)

| Temporada | Costo | Precio al cliente | Ganancia | Margen |
|---|---|---|---|---|
| Baja | $60 | $80 | $20 | 25% |
| Media | $60 | $85 | $25 | 30% |
| Alta | $70-$80 | $100-$110 | $30-$35 | 35% |

**Apartamentos grandes** (costo propietario 8-10 pax, $90-$120)

| Temporada | Costo | Precio al cliente | Ganancia | Margen |
|---|---|---|---|---|
| Baja | $90 | $110 | $20 | 25% |
| Media | $90 | $115-$120 | $25-$30 | 30-35% |
| Alta | $100 | $135-$140 | $35-$40 | 40-45% |

## Calendario de temporadas

| Período | Temporada |
|---|---|
| 1-15 enero | Alta |
| Resto de enero | Media |
| Febrero (sin carnaval) | Baja |
| Carnaval (semana completa) | Alta |
| Marzo | Media |
| Semana Santa (semana completa) | Alta |
| Resto de abril | Baja |
| Mayo | Baja |
| Junio | Media |
| Julio (primeras semanas) | Media |
| Agosto (sobre todo 2ª mitad) | Alta |
| Septiembre | Media |
| Octubre | Baja |
| Noviembre | Media |
| 15 dic - 5 ene | Alta |

Estrategia por temporada:

- **Baja** — el precio sí importa. Objetivo: ocupación y flujo, ganar por
  volumen.
- **Media** — rango flexible y negociable. Objetivo: capturar reservas
  anticipadas de temporada alta.
- **Alta** — la demanda manda y el precio deja de ser el factor principal. Se
  reserva el precio fuerte para últimas unidades y reservas de último momento.

Nota práctica: al fechar un análisis, ubica la fecha en este calendario y dilo
explícitamente. Un análisis hecho en julio que razona con precios de agosto está
razonando sobre temporada alta, no media.

## El margen es una restricción, no una sugerencia

Ningún precio recomendado puede dejar menos del margen mínimo. Cuando el mercado
no permite alcanzarlo, la salida no es recortar la utilidad de Llégate — que ya
está en el hueso — sino renegociar con el propietario o reperfilar la propiedad.

**MODO DEFENSIVO** es la única excepción. Naylu lo activa escribiéndolo
explícitamente, y significa colocar una propiedad sí o sí (fecha muerta,
propietario presionando, unidad nueva que necesita primeras reseñas). En ese
modo se puede bajar del mínimo, pero el entregable debe declarar:

- cuánto margen se sacrifica por noche,
- por cuántas noches aplica,
- y cuál es el precio de retorno una vez pasada la situación.

Un descuento sin fecha de reversión se vuelve el precio nuevo. Eso es lo que hay
que evitar.

## Cálculo del precio sugerido

```
precio_minimo_viable = costo_base_propiedad + margen_objetivo
```

Donde `margen_objetivo` sale de la sección de realidad de mercado vigente ($15-
$20 general, hasta $25 en grandes, mínimo $20 como norte).

Luego se contrasta contra el mercado:

```
brecha = precio_minimo_viable - mediana_comparables_ajustados
```

Interpretación:

| Brecha | Lectura | Salida |
|---|---|---|
| Menor a -$10 | Hay espacio de mercado sin usar | Subir precio al huésped |
| Entre -$10 y +$5 | Competitivo, colchón justo | Mantener y vigilar |
| Entre +$5 y +$15 | Caro; se vende solo por diferenciación | Renegociar o reperfilar |
| Mayor a +$15 | El costo del propietario impide competir | Renegociar, prioridad alta |

La brecha positiva casi nunca se arregla bajando el margen de Llégate. Con
márgenes de $15-$20 ya no hay de dónde recortar. Se arregla con el propietario.

## Argumentos para negociar con propietarios

Cuando el entregable sea para una conversación con un propietario, el análisis
debe traducirse a un argumento, no a una tabla.

El argumento que funciona es **facturar contra esperar**: el propietario no
elige entre $115 y $95. Elige entre $95 con ocupación y $115 con la unidad
vacía. Un mes vacío a $115 rinde cero; veinte noches a $95 rinden $1.900.

Elementos que hacen creíble ese argumento:

1. **El comparable concreto.** No "el mercado está en $75", sino "hay tres
   unidades de 3 habitaciones en la misma zona publicadas entre $70 y $85 en
   Airbnb, con enlaces verificables". La especificidad es lo que convence.
2. **El número exacto que se pide.** Una cifra, no un rango vago.
3. **La comparación de ingreso mensual**, no de tarifa noche. El propietario
   piensa en la tarifa; hay que moverlo a pensar en el ingreso.
4. **Reconocer lo que la unidad tiene de bueno.** Los atributos de Notion
   sirven aquí. Un propietario que siente que le están devaluando su propiedad
   se cierra.

Los propietarios sobrevaloran por apego emocional, por comparar con referencias
malas (lo que pidió el vecino) y por recordar precios de años buenos. El
argumento no debe pelear con eso: debe ofrecer datos externos y verificables que
reemplacen la referencia mala por una buena.

Advertencia de encuadre: la cartera **no está sobrevalorada de forma general**.
El problema se concentra en propietarios y unidades específicas. Presentar una
conclusión global es falso y además desarma la negociación puntual, que es donde
está el valor.
