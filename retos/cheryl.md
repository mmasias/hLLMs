# El cumpleaños de Cheryl

## Enunciado

Albert y Bernard acaban de hacerse amigos de Cheryl y quieren saber cuándo es su cumpleaños. Cheryl les da una lista de 10 fechas posibles:

- 15 de mayo, 16 de mayo, 19 de mayo
- 17 de junio, 18 de junio
- 14 de julio, 16 de julio
- 14 de agosto, 15 de agosto, 17 de agosto

Luego Cheryl les dice a Albert y a Bernard **por separado** el mes y el día de su cumpleaños, respectivamente.

- **Albert:** "No sé cuándo es el cumpleaños de Cheryl, pero sé que Bernard tampoco lo sabe."
- **Bernard:** "Al principio no sabía cuándo es el cumpleaños de Cheryl, pero ahora sí lo sé."
- **Albert:** "Entonces yo también ya sé cuándo es el cumpleaños de Cheryl."

## Respuesta correcta

**16 de julio.**

## Resolución

1. Bernard solo sabría directamente si el día fuera único. Los días únicos son 18 (solo en junio) y 19 (solo en mayo). Albert *sabe que Bernard no lo sabe*, lo que significa que el mes que Albert conoce no contiene ningún día único. Mayo tiene el 19 y junio tiene el 18 → se eliminan mayo y junio completos.

2. Quedan: 14 julio, 16 julio, 14 agosto, 15 agosto, 17 agosto. Bernard ahora sabe la fecha. Si el día fuera 14, no podría decidir (14 aparece en julio y agosto). Así que el día no es 14. Quedan: 16 julio, 15 agosto, 17 agosto.

3. Albert también sabe. Si el mes fuera agosto, Albert no podría decidir (agosto tiene dos opciones: 15 y 17). Así que el mes es julio → **16 de julio**.

## Por qué es buen test para LLMs

Requiere modelar el conocimiento de otros agentes (teoría de la mente), razonar por eliminación en cascada, y mantener el estado a lo largo de tres turnos lógicos. La mayoría de LLMs fallan en al menos uno de estos pasos.
