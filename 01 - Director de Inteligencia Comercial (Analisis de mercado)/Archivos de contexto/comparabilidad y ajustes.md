# Comparabilidad, segmentos y ajustes de precio

## Segmento comercial: el filtro que va primero

Antes de comparar números, verifica que las dos propiedades **compitan de
verdad**. Un frente de playa no compite con un apartamento estándar aunque
ambos tengan 2 habitaciones y capacidad para 6: no se venden al mismo cliente ni
por las mismas razones.

Comparar entre segmentos distintos produce las dos conclusiones falsas más
comunes: creer que una propiedad premium está cara, y creer que una económica es
una ganga.

Segmentos que aplican en Lechería:

| Segmento | Señas |
|---|---|
| **Premium / frente al mar** | Salida directa a la playa, vista al mar, muelle privado, acabados superiores |
| **Medio** | Buenas amenidades, piscina, mantenimiento correcto, sin acceso directo a playa |
| **Económico** | Poca modernidad, áreas comunes deterioradas, sin ascensor o sin piscina |
| **Corporativo / laboral** | Capacidad alta, cocina y lavandería completas, cercanía a zona de trabajo. La piscina importa poco |
| **Familiar / grupos grandes** | Capacidad de 8 o más, varios baños, áreas sociales |
| **Parejas / estadía corta** | 1 habitación, capacidad de 2 a 4, ubicación céntrica |

Una propiedad puede pertenecer a más de un segmento. Doral Beach TH es premium
por playa privada y a la vez familiar por capacidad.

Para clasificar, usa los campos `Plus`, `Servicios`, `Puntos Criticos` y
`Target` del Inventario maestro, más los atributos de Notion. **No inventes el
segmento**: si los datos no alcanzan para clasificar, dilo.

En el benchmark el segmento no viene declarado; se deduce de zona, amenidades y
notas del anuncio. Cuando la deducción sea dudosa, márcala como supuesto.

## Niveles de comparabilidad

Cuatro niveles, de mejor a peor. La regla práctica: cuanto más bajo el nivel,
más reservas hay que poner en la conclusión.

### Nivel A — comparable perfecto

Misma urbanización, mismas habitaciones, misma capacidad, amenidades similares.
Es el mejor comparable que existe: mismo edificio, mismas áreas comunes, misma
ubicación exacta. La conclusión se enuncia con firmeza.

Ejemplo: Costa Guaica 3 hab / 6 pax contra otro Costa Guaica 3 hab / 6 pax.

### Nivel B — misma zona, capacidad cercana

Misma zona, mismas habitaciones, capacidad con diferencia de hasta 2 personas,
amenidades y segmento similares. Comparación sólida; se declara la diferencia de
capacidad.

### Nivel C — una habitación de diferencia

Misma zona, una habitación de diferencia, capacidad similar, mismo segmento.
Sirve como referencia de rango, no para fijar un precio exacto. Analiza por
precio por persona.

### Nivel D — otra urbanización, mismo segmento

Otra urbanización pero mismo segmento comercial y amenidades equivalentes. Es el
piso de lo utilizable. Da contexto de mercado; no sostiene por sí solo una
recomendación de precio.

### Sin comparable

Nada que cumpla los criterios anteriores. **No se emite veredicto de precio.** Se
declara el hueco y se especifica qué buscar.

Es preferible una fila que diga "sin comparable" a una conclusión construida
sobre un comparable forzado. Naylu usa estos números frente a propietarios; un
número débil presentado como firme se le devuelve en la cara.

**Sobre los pesos numéricos:** la tentación es asignar 100%, 85%, 70% y 50% a
los niveles y promediar ponderado. No lo hagas. Esos porcentajes son inventados
y su única función real sería disfrazar de precisión una decisión de criterio.
Muestra el nivel de cada comparable, calcula la mediana de los del mejor nivel
disponible, y deja que el nivel comunique la confianza.

Si en un mismo análisis conviven niveles distintos, prioriza los mejores. Cinco
comparables de nivel D no equivalen a uno de nivel A.

## El ajuste de Mercado Libre: tres escenarios

Todos los anuncios de Mercado Libre del benchmark están gestionados por
inmobiliarias. La comisión estimada es de **$20 a $30 por noche**, ya incluida en
el precio publicado.

No descuentes automáticamente y en silencio. Presenta los tres escenarios, para
que el supuesto quede a la vista y Naylu pueda cuestionarlo:

| Escenario | Cálculo | Para qué sirve |
|---|---|---|
| **Precio publicado** | Tal cual aparece | Es lo que el huésped ve al comparar. Referencia del techo de mercado |
| **Precio sin comisión** | Publicado − $20 a $30 | Aproxima lo que recibe el propietario. Referencia para negociar costos |
| **Precio competitivo final** | Criterio, dentro del rango anterior | El número que se usa para la mediana de mercado |

Cuando la decisión cambiaría según se use $20 o $30, muestra el rango completo
en vez de un punto medio:

> Marina del Rey ML: $100 publicado → $70–$80 sin comisión

Cuando la nota del anuncio ya trae el costo estimado al propietario (algunas
filas lo dicen explícitamente), **usa esa cifra en vez del rango genérico**: es
información específica de esa unidad y vale más que una regla general.

Los precios de Airbnb **no se ajustan**: son mayormente de anfitriones directos y
reflejan lo que el mercado paga.

**Cuidado con el ajuste en anuncios baratos.** Restar $25 a un anuncio de $35
deja $10, que no es un precio real de nada. Cuando el descuento se lleve más de
un tercio del precio publicado, la comisión fija probablemente no aplica igual:
o el anuncio es de un producto más pequeño, o la inmobiliaria cobra menos ahí.
En esos casos usa el precio publicado como referencia y señala la duda, en vez
de arrastrar un número imposible hasta la mediana.

## Comparar cuando la capacidad no coincide

El huésped no compara "apartamentos de 2 habitaciones". Compara **capacidad y
precio total para su grupo**. Por eso la capacidad pesa tanto como las
habitaciones.

Cuando la capacidad no coincide, compara precio por persona:

```
precio_por_persona = precio_noche / capacidad_maxima
```

El razonamiento esperado, con un ejemplo: una unidad de 3 habitaciones para 8
personas a $115 son $14,4 por persona. El comparable de 3 habitaciones para 6
personas a $75 son $12,5 por persona. La unidad propia es más cara por persona,
pero absorbe un grupo que el comparable no puede alojar — ese grupo tendría que
alquilar dos unidades. Eso no es una desventaja de precio: es un argumento de
venta.

El razonamiento inverso también aplica: si una unidad de 3 habitaciones para 6
personas sale más cara por persona que dos unidades pequeñas juntas, tiene un
problema competitivo real.

## Cotización escalonada por tamaño de grupo

Naylu puede maximizar rentabilidad cotizando por número de personas en vez de un
precio fijo. La lógica: una unidad grande vacía pierde frente a una pequeña bien
tarifada.

Esto es especialmente relevante porque la demanda real se concentra en grupos de
4 a 6 personas (ver `demanda-y-rotacion.md`). Las unidades de 8 a 10 pax están
compitiendo por una porción pequeña del mercado.

Cuando una unidad tenga `Capacidad Base` bastante menor que `Capacidad Max`, o
tipo de tarifa `Escalonada` o `Incremento`, propón una tabla de cotización por
tramo, comparando cada uno contra el comparable de esa capacidad.

La pregunta que responde: para un grupo de 4, ¿esta unidad grande a tarifa
reducida compite contra una unidad pequeña del mercado? Si sí, hay ingreso
recuperable que hoy se pierde. Si no, esa unidad debe enfocarse solo en grupos
grandes, y hay que decirlo.

Verifica que **cada tramo** respete el margen mínimo. Un tramo que llena la
unidad pero deja $8 de margen no resuelve nada — y viola la restricción de
margen de la skill.
