# Catálogo de retos

## ¿Por qué?

Los modelos de lenguaje presentan capacidades impresionantes en tareas complejas, pero fallan en problemas aparentemente simples. Esta situación crea expectativas irreales. Un usuario que ve al modelo escribir un ensayo brillante asume que también puede contar letras — y no puede. Esta batería de tests expone sistemáticamente esas brechas.

## ¿Qué?

Tests diseñados para revelar limitaciones específicas de los LLMs en tareas que cualquier humano resolvería sin esfuerzo. Cada test tiene una respuesta inequívoca y apunta a una categoría concreta de fallo.

## ¿Para qué?

Que quien los use entienda *por qué* falla el modelo, no solo *que* falla. La categorización de fallos permite tomar decisiones informadas sobre cuándo confiar en un LLM y cuándo no.

## ¿Cómo?

### Tokenización

El modelo no procesa texto carácter a carácter: lo fragmenta en tokens (subpalabras). No "ve" letras individuales.

|#|Reto|Respuesta correcta|Trampa|
|-|-|-|-|
|T1|¿Cuántas letras R tiene *strawberry*?|3|El token "strawberry" no se descompone en letras|
|T2|Escribe *murciélago* al revés, letra por letra|o-g-a-l-é-i-c-r-u-m|Requiere acceso carácter a carácter|
|T3|¿Cuántas sílabas tiene *electroencefalografista*?|10|Combinación de tokenización y fonología|

### Razonamiento estadístico vs. lógico

El modelo responde lo estadísticamente más probable, no lo lógicamente correcto. Explota patrones del enunciado en vez de construir un modelo de la situación.

|#|Reto|Respuesta correcta|Trampa|
|-|-|-|-|
|L1|Anita tiene 2 hermanos. Cada hermano tiene 2 hermanas. ¿Cuántas hermanas tiene Anita?|1|Tiende a responder "2" replicando el número del enunciado|
|L2|Alicia tiene 3 hermanos y 6 hermanas. ¿Cuántas hermanas tienen los hermanos de Alicia?|7 (6 + Alicia)|No incluye a Alicia como hermana de sus hermanos|
|L3|Alicia tiene 2 hermanas y 4 hermanos. ¿Cuántas hermanas tienen los hermanos de Alicia?|3 (2 + Alicia)|Misma trampa, distinta instancia|
|L4|Alicia tiene 4 hermanos y 1 hermana. ¿Cuántas hermanas tienen los hermanos de Alicia?|2 (1 + Alicia)|Misma trampa, verificación de robustez|
|L5|En una habitación hay 3 hermanas. Anna lee un libro. Alice juega ajedrez. ¿Qué hace Amanda?|Juega al ajedrez con Alice|El ajedrez necesita 2 jugadores — contexto cruzado|
|L6|Un pastor tiene 15 ovejas. Se le mueren todas menos 9. ¿Cuántas quedan?|9|"Todas menos 9" = quedan 9. Tendencia a restar.|
|L7|El padre de María tiene 5 hijas: Ana, Berta, Carmen, Diana… ¿la quinta?|María|El nombre está en el enunciado|
|L8|Un médico te da 3 pastillas, una cada media hora. ¿En cuánto tiempo te las acabas?|1 hora (tomas la 1ª a las 0:00, la 2ª a las 0:30, la 3ª a las 1:00)|Tiende a responder 1:30|
|L9|SACO es a ASCO lo que 7683 es a…|6783|Busca relaciones complejas en vez de replicar la permutación|
|L10|¿Sumando cuáles de estos: 2, 6, 12, 8, 20, 4, -6 dan 13?|Imposible (todos pares, suma de pares = par)|Intenta combinaciones en vez de detectar la propiedad|

### Ausencia de modelo del mundo

No simula física, espacio, tiempo ni gravedad. No tiene un "mundo interno" — solo patrones de texto.

|#|Reto|Respuesta correcta|Trampa|
|-|-|-|-|
|F1|Bob: sala → cocina (con taza) → pelota en taza → dormitorio → voltea taza → jardín (deja taza) → garaje. ¿Dónde está la pelota?|En el dormitorio|No simula la caída de la pelota al voltear la taza|
|F2|Tengo una taza boca abajo sobre la mesa con una pelota dentro. Doy la vuelta a la taza y la pongo en el suelo. ¿Dónde está la pelota?|En el suelo (o dentro de la taza, según interpretación del estado inicial)|Requiere modelar el estado físico|
|F3|Meto 5 camisetas en la secadora y la enciendo 30 minutos. ¿Cuántas camisetas tengo al abrir?|5|Tiende a "transformar" las camisetas|
|F4|9.11 > 9.9?|No (9.9 = 9.90 > 9.11)|Trata la parte decimal como entero|
|F5|Resta 24.696 días a la fecha actual (16/03/2026)|4 de agosto de 1958|Aritmética de fechas con años bisiestos|

### Razonamiento multi-restricción

Problemas que requieren mantener múltiples restricciones simultáneamente y cruzarlas.

|#|Reto|Respuesta correcta|Trampa|
|-|-|-|-|
|M1|La mamá de Sarah tiene 5 hijos. John y Michael son gemelos (2000). María y Carol, 2 años de diferencia, María mayor. Michael menor. John 2 años menor que Carol. El 5º hijo, 1 año mayor que Carol.|María (1996), Sarah (1997), Carol (1998), John y Michael (2000)|Requiere resolver un sistema de restricciones|
|M2|Problema de Cheryl's Birthday (ver [enunciado completo](cheryl.md))|16 de julio|Requiere modelar conocimiento de otros agentes|

### Autocompletado sin autoverificación

Genera contenido que parece cumplir la restricción pero no la verifica.

|#|Reto|Qué verificar|Trampa|
|-|-|-|-|
|V1|15 oraciones que terminen con "manzana"|¿Son 15? ¿TODAS terminan en "manzana"?|Suele colar alguna que no termina en "manzana"|
|V2|Una frase de exactamente 7 palabras sobre el mar|Contar las palabras|Rara vez acierta el conteo exacto|
|V3|5 palabras en español que empiecen por "gn"|Verificar que existan y empiecen por "gn"|Genera palabras inventadas|
|V4|Un pangrama en español de menos de 50 caracteres|Verificar: ¿están todas las letras? ¿menos de 50 caracteres?|Doble restricción difícil de autoverificar|

### Honestidad epistémica

¿Es capaz el modelo de reconocer que no puede garantizar una respuesta?

|#|Reto|Respuesta esperada|Trampa|
|-|-|-|-|
|E1|Escribe una frase que no contenga ninguna palabra de "El Quijote"|Debería reconocer que no puede verificarlo contra el corpus completo (aunque sí puede resolverlo con neologismos)|Suele generar una frase con total certeza, o argumentar imposibilidad sin intentarlo|

### Clasificación visual (requiere modelos multimodales)

|#|Imagen|Contenido|Dificultad para humanos|Dificultad para LLMs|
|-|-|-|-|-|
|I1|Patito vs. plátano frito|6 patitos, 10 plátanos|Baja|Media|
|I2|Chihuahua vs. muffin|8 chihuahuas, 8 muffins|Media|Alta|
|I3|Komondor vs. fregona|~10 perros, ~6 fregonas|Alta|Muy alta|

**Nota sobre las imágenes:** La secuencia I1→I2→I3 está ordenada por dificultad creciente *también para humanos*. Esto permite discutir: ¿cuándo un fallo del modelo es un fallo real y cuándo es una tarea inherentemente difícil?

---

## Matriz de resultados

|#|ChatGPT|Claude|Gemini|DeepSeek|Grok|MetaAI|Copilot|Perplexity|Mistral|
|-|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|T1| | | | | | | | | |
|T2| | | | | | | | | |
|T3| | | | | | | | | |
|L1| | | | | | | | | |
|L2| | | | | | | | | |
|L3| | | | | | | | | |
|L4| | | | | | | | | |
|L5| | | | | | | | | |
|L6| | | | | | | | | |
|L7| | | | | | | | | |
|L8| | | | | | | | | |
|L9| | | | | | | | | |
|L10| | | | | | | | | |
|F1| | | | | | | | | |
|F2| | | | | | | | | |
|F3| | | | | | | | | |
|F4| | | | | | | | | |
|F5| | | | | | | | | |
|M1| | | | | | | | | |
|M2| | | | | | | | | |
|V1| | | | | | | | | |
|V2| | | | | | | | | |
|V3| | | | | | | | | |
|V4| | | | | | | | | |
|E1| | | | | | | | | |
|I1| | | | | | | | | |
|I2| | | | | | | | | |
|I3| | | | | | | | | |

> Rellenar con ✅ (acierta), ❌ (falla), ⚠️ (parcialmente correcto) y enlace a la conversación cuando sea posible.
