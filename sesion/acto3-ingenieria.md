# Acto 3 — "Esto es ingeniería" (35 min)

## Objetivo

Demostrar que el mismo modelo, con distinto prompt, da resultados radicalmente diferentes. El prompt no es decoración: es ingeniería.

## Dinámica

### Demostración frontal: el caso de Bob (5 min)

Usar el problema de Bob (reto #9 del Acto 2) como demostración en vivo. Primero recordar que falló. Luego lanzar el prompt de "tres expertos":

```
Imagina que tres expertos diferentes están respondiendo a esta pregunta.
Todos los expertos escribirán un paso de su pensamiento, luego lo compartirán con el grupo.
Luego, todos los expertos pasarán al siguiente paso, etc.
Si algún experto se da cuenta de que está equivocado en algún momento, entonces se retirará.
La pregunta es:

Bob está en la sala de estar.
Camina hacia la cocina, llevando una taza.
Él pone una pelota en la taza y lleva la taza al dormitorio.
Voltea la taza boca abajo y luego camina hacia el jardín.
Pone la taza en el jardín y luego camina hacia el garaje.
¿Dónde está la pelota?
```

Proyectar la respuesta. El modelo ahora probablemente acierta. La reacción esperada: "¿Solo con cambiar la pregunta?"

Sí. Solo con eso.

### Presentación de técnicas (5 min)

Explicar brevemente las tres técnicas que van a usar. No teorizar: definir y dar ejemplo.

#### 1. Chain of Thought (cadena de pensamiento)

Forzar al modelo a razonar paso a paso antes de responder.

> **Truco:** Añadir "Razona paso a paso antes de dar la respuesta final" al final de cualquier pregunta.

#### 2. Descomposición

Partir la tarea en subtareas que el modelo pueda verificar individualmente.

> **Truco:** En vez de "¿Cuántas R tiene strawberry?", pedir "Primero escribe la palabra letra por letra, una por línea. Luego cuenta las R."

#### 3. Few-shot (aprendizaje con ejemplos)

Darle ejemplos resueltos antes de la pregunta real.

> **Truco:** "Ejemplo: CASA es a ASAC lo que MESA es a ASEM. Ahora: SACO es a ASCO lo que 7683 es a…"

### Trabajo en grupos (20 min)

Cada grupo elige **3 retos que fallaron** en el Acto 2 e intenta resolverlos aplicando las técnicas. Disponen de los [prompts preparados](../recursos/prompts-preparados.md) como punto de partida, pero se les anima a experimentar con sus propias variaciones.

Registran en la tabla compartida:

- Reto original
- Técnica aplicada
- Prompt modificado
- ¿Funcionó?

**Lo que van a descubrir por sí mismos:**

- Chain of thought resuelve muchos problemas de lógica (hermanas, paridad).
- Descomposición resuelve los de conteo y manipulación de caracteres.
- Few-shot ayuda en los analógicos (SACO/ASCO).
- Algunos problemas resisten todas las técnicas — y eso también es información.
- El mismo prompt funciona distinto en distintos modelos.

### Puesta en común rápida (5 min)

Cada grupo comparte: qué reto recuperaron, con qué técnica, y si alguno resistió todo.

**Mensaje clave:**

> "No es magia. Es saber cómo funciona la herramienta. Como con cualquier herramienta: si no sabes usarla, el resultado es impredecible. Si sabes, es útil."
