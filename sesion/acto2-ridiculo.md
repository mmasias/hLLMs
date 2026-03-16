# Acto 2 — "Esto es ridículo" (35 min)

## Objetivo

Romper la confianza construida en el Acto 1. Que descubran que el modelo falla en cosas que ellos resuelven sin esfuerzo.

## Dinámica

### Fase de trabajo en grupos (20-25 min)

Cada grupo recibe los retos (se pueden dictar, compartir por chat o proyectar de uno en uno). Los lanzan a sus LLMs y registran resultados en la [plantilla compartida](../recursos/plantilla-registro.md).

**Orden recomendado** (de impacto inmediato a conceptualmente más profundo):

#### Bloque 1 — Impacto instantáneo (5 min)

Retos donde la verificación es inmediata y el fallo es espectacular:

|#|Reto|Respuesta correcta|Categoría de fallo|
|-|-|-|-|
|1|¿9.11 es mayor que 9.9?|No. 9.9 > 9.11|Aritmética: trata decimales como enteros|
|2|¿Cuántas letras R tiene la palabra *strawberry*?|3|Tokenización: no "ve" letras, ve tokens|
|3|Escribe *murciélago* al revés, letra por letra|o-g-a-l-é-i-c-r-u-m|Tokenización|

#### Bloque 2 — Trampas lógicas (10 min)

Retos donde el enunciado contiene una trampa que explota el patrón estadístico:

|#|Reto|Respuesta correcta|Categoría de fallo|
|-|-|-|-|
|4|Anita tiene dos hermanos. Cada hermano tiene dos hermanas. ¿Cuántas hermanas tiene Anita?|1 (Anita + su hermana = las 2 hermanas de los hermanos)|Razonamiento: replica números del enunciado sin modelar|
|5|Alicia tiene 3 hermanos y 6 hermanas. ¿Cuántas hermanas tienen los hermanos de Alicia?|7 (las 6 hermanas + Alicia)|Razonamiento: no incluye a Alicia como hermana|
|6|En una habitación hay 3 hermanas. Anna lee un libro. Alice juega una partida de ajedrez. ¿Qué hace Amanda?|Juega al ajedrez con Alice (el ajedrez requiere 2 jugadores)|Razonamiento: procesa oraciones sin contexto cruzado|
|7|SACO es a ASCO lo que 7683 es a…|6783 (se intercambian las dos primeras posiciones)|Razonamiento analógico: busca relaciones complejas en lugar de replicar la permutación|
|8|¿Sumando cuáles de estos números: 2, 6, 12, 8, 20, 4, -6 puedes obtener 13?|Imposible: todos son pares, la suma de pares siempre es par|Razonamiento: intenta fuerza bruta en vez de detectar la propiedad|

#### Bloque 3 — Razonamiento físico (5 min)

|#|Reto|Respuesta correcta|Categoría de fallo|
|-|-|-|-|
|9|Bob está en la sala. Camina a la cocina con una taza. Pone una pelota en la taza y la lleva al dormitorio. Voltea la taza boca abajo y camina al jardín. Deja la taza en el jardín y va al garaje. ¿Dónde está la pelota?|En el dormitorio (al voltear la taza, la pelota cae)|Ausencia de modelo físico: no simula gravedad|
|10|La mamá de Sarah tiene 5 hijos: John y Michael son gemelos (nacidos en 2000). María y Carol nacieron con 2 años de diferencia, María es la mayor. Michael es el menor. John es 2 años más joven que Carol. El quinto hijo es 1 año mayor que Carol. ¿Nombres y años?|María (1996), Sarah (1997), Carol (1998), John (2000), Michael (2000)|Razonamiento multi-restricción|

#### Bloque 4 — Generación con restricciones (5 min)

|#|Reto|Qué observar|Categoría de fallo|
|-|-|-|-|
|11|Escribe una frase que no contenga ninguna palabra de "El Quijote"|Si genera una frase sin verificar — o si argumenta que es imposible sin intentar (neologismos, anglicismos)|Falsa certeza o sobreargumentación de imposibilidad|
|12|Dime 15 oraciones que terminen con la palabra "manzana"|Contar si son 15, verificar que TODAS terminen en "manzana"|Autocompletado sin autoverificación|
|13|Resta 24.696 días a la fecha de hoy|4 de agosto de 1958 (desde 16/03/2026). Verificar: años bisiestos|Aritmética de fechas: intenta calcular "de cabeza"|

#### Bloque 5 — Visual (si hay acceso multimodal) (5 min)

Mostrar las imágenes una por una. Cada grupo pregunta al LLM: "¿Cuántos X hay en esta imagen?"

|#|Imagen|Qué es|Dificultad|
|-|-|-|-|
|14|Patitos vs. plátano frito|*Duckling or Fried Plantain*|Media|
|15|Chihuahua vs. muffin|*Chihuahua or Muffin* (@teenybiscuit)|Alta|
|16|Komondor vs. fregona|*Komondor or Mop*|Muy alta|

**Nota:** El orden va de menor a mayor dificultad incluso para humanos. Esto permite introducir la pregunta: "Si nosotros también dudamos, ¿es justo decir que el LLM ha fallado?"

---

### Fase de puesta en común (10 min)

Cada grupo presenta al pleno su fallo más espectacular. En pizarra (o en el documento compartido) se agrupan los fallos por **causa raíz**:

|Causa raíz|Explicación breve|Retos donde aparece|
|-|-|-|
|**Tokenización**|El modelo no ve letras ni caracteres: ve tokens (fragmentos de texto). No puede contar lo que no ve.|2, 3|
|**Razonamiento estadístico**|Responde lo más probable según sus datos de entrenamiento, no lo lógicamente correcto.|4, 5, 6, 7, 8|
|**Ausencia de modelo del mundo**|No simula física, espacio ni tiempo. No tiene gravedad, no tiene calendario.|1, 9, 10, 13|
|**Autocompletado sin verificación**|Genera contenido que parece correcto pero no verifica sus propias restricciones.|11, 12|
|**Falsa certeza**|Presenta respuestas incorrectas con total confianza. No dice "no sé".|11, 14-16|

**Mensaje clave para cerrar el Acto 2:**

> "No es que sea tonto. Es que no piensa. Predice la siguiente palabra más probable. Y a veces lo probable no es lo correcto."

Transición directa al Acto 3:

> "Pero… ¿y si le obligamos a pensar?"
