# Prompts preparados para el Acto 3

Prompts listos para copiar y pegar. Los alumnos pueden usarlos tal cual o modificarlos.

---

## Tree of Thought — "Tres expertos"

Aplicable a: problemas de lógica, razonamiento espacial, multi-restricción.

```
Imagina que tres expertos diferentes están respondiendo a esta pregunta.
Todos los expertos escribirán un paso de su pensamiento, luego lo compartirán con el grupo.
Luego, todos los expertos pasarán al siguiente paso, etc.
Si algún experto se da cuenta de que está equivocado en algún momento, entonces se retirará.
La pregunta es:

[PEGAR EL RETO AQUÍ]
```

---

## Chain of Thought — Razonamiento paso a paso

Aplicable a: problemas de lógica, aritmética, relaciones familiares.

```
Resuelve el siguiente problema paso a paso. Muestra cada paso de tu razonamiento antes de dar la respuesta final.

[PEGAR EL RETO AQUÍ]
```

Variante más directiva:

```
Antes de responder, analiza el problema así:
1. Identifica qué datos te dan.
2. Identifica qué te piden.
3. Razona cada paso intermedio.
4. Verifica tu respuesta antes de darla.

Problema: [PEGAR EL RETO AQUÍ]
```

---

## Descomposición — Subtareas verificables

Aplicable a: conteo de letras, manipulación de caracteres, restricciones formales.

Para conteo de letras:
```
Escribe la palabra "strawberry" separada letra por letra, una por línea, numerando cada letra. Luego cuenta cuántas veces aparece la letra R.
```

Para escribir al revés:
```
Escribe la palabra "murciélago" letra por letra, una por línea, numerando cada posición. Luego escribe las letras en orden inverso, de la última a la primera.
```

Para generación con restricción de conteo:
```
Escribe una frase sobre el mar. La frase debe tener exactamente 7 palabras. Después de escribirla, numera cada palabra para verificar que son 7.
```

---

## Few-shot — Ejemplos previos

Aplicable a: analogías, patrones, transformaciones.

Para el reto SACO/7683:
```
Voy a darte un patrón con un ejemplo y luego una pregunta.

Ejemplo: CASA es a ACSA lo que MESA es a EMSA
(La transformación es: intercambiar las dos primeras letras)

Ahora, con la misma lógica:
SACO es a ASCO lo que 7683 es a...
Identifica primero la transformación en las letras y luego aplícala a los números.
```

Para las relaciones familiares:
```
Ejemplo resuelto:
"Pedro tiene 1 hermano. Su hermano tiene 1 hermana. ¿Cuántas hermanas tiene Pedro?"
Razonamiento: Pedro y su hermano son 2 varones. El hermano tiene 1 hermana → esa hermana es hermana de ambos. Pedro tiene 1 hermana.

Ahora resuelve con el mismo razonamiento:
"Anita tiene 2 hermanos. Cada hermano tiene 2 hermanas. ¿Cuántas hermanas tiene Anita?"
```

---

## Adversarial — Autoverificación forzada

Aplicable a: cualquier reto donde el modelo respondió con falsa certeza.

```
Resuelve el siguiente problema. Después de dar tu respuesta, actúa como un crítico que intenta encontrar errores en tu propio razonamiento. Si encuentras un error, corrígelo.

[PEGAR EL RETO AQUÍ]
```

Variante para imposibilidad:

```
Antes de intentar resolver esto, analiza si el problema tiene solución. Examina las propiedades matemáticas de los datos. Solo si tiene solución, resuélvelo.

[PEGAR EL RETO AQUÍ]
```

---

## Combinación — Para los retos más difíciles

Para el cumpleaños de Cheryl:
```
Vamos a resolver esto construyendo una tabla de eliminación.

Paso 1: Lista todas las fechas posibles.
Paso 2: Analiza qué significa que Albert SEPA que Bernard no sabe. ¿Qué meses elimina esto?
Paso 3: Con las fechas restantes, analiza qué significa que Bernard ahora SÍ sabe. ¿Qué días elimina?
Paso 4: Con las fechas restantes, analiza qué significa que Albert ahora también sabe. ¿Qué meses elimina?
Paso 5: La fecha restante es la respuesta.

Problema: [PEGAR ENUNCIADO COMPLETO]
```
