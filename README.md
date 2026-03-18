# Hackeando LLMs

<div align=right>

<sub><i>Los humanos siempre hemos tenido que lidiar con nuevas formas de expresión.<br>A ustedes les ha tocado una que no solo habla, sino que además responde.</i></sub>

</div>

## ¿Por qué?

||||
|-|-|-|
Muchos usuarios de los modelos de lenguaje los utilizan como si de oráculos se tratase: les preguntan (*si es que preguntan!!!*) y aceptan sus respuestas.|No cuestionan las respuestas ni distinguen cuándo el modelo razona de cuándo improvisa.|Desconocen que la forma de preguntar puede cambiar radicalmente la respuesta.

## ¿Qué?

<div align=center>

|[![](https://img.shields.io/badge/-ChatGPT-FFF?style=flat&logo=openai&logoColor=black)](https://chat.openai.com/) [![](https://img.shields.io/badge/-Claude-FFF?style=flat&logo=anthropic&logoColor=black)](https://claude.ai/chats) [![](https://img.shields.io/badge/-Gemini-FFF?style=flat&logo=googlegemini&logoColor=black)](https://gemini.google.com/app) [![](https://img.shields.io/badge/-DeepSeek-FFF?style=flat&logo=deepseek&logoColor=black)](https://chat.deepseek.com/) [![](https://img.shields.io/badge/-Grok-FFF?style=flat&logo=x&logoColor=black)](https://x.com/i/grok) [![](https://img.shields.io/badge/-MetaAI-FFF?style=flat&logo=meta&logoColor=black)](https://www.meta.ai/) [![](https://img.shields.io/badge/-Copilot-FFF?style=flat&logo=microsoft&logoColor=black)](https://copilot.microsoft.com/)<br>[![](https://img.shields.io/badge/-Perplexity-FFF?style=flat&logo=perplexity&logoColor=black)](https://www.perplexity.ai/) [![](https://img.shields.io/badge/-Mistral-FFF?style=flat)](https://chat.mistral.ai/chat) [![](https://img.shields.io/badge/-Qwen-FFF?style=flat&logo=qwen&logoColor=black)](https://chat.qwen.ai/) [![](https://img.shields.io/badge/-Z.Ai-FFF?style=flat&logo=&logoColor=black)](https://https://chat.z.ai/) [![](https://img.shields.io/badge/-Google-FFF?style=flat&logo=google&logoColor=black)](https://www.google.com/)
|:-:|
LLMs: Modelos de lenguaje de gran escala / Large language models

</div>

Los modelos de lenguaje de gran escala (LLMs) son sistemas de inteligencia artificial entrenados con enormes cantidades de texto para entender y generar lenguaje humano de forma natural. Estos modelos aprenden patrones, contexto y relaciones del lenguaje mediante técnicas de aprendizaje automático, permitiendo procesar y producir texto coherente y contextualmente apropiado.

<div align=right>

O sea, como el autocompletar ([¿o no? 🤔](https://github.com/mmasias/ai-prompts/blob/main/documentos/casosDeUso/conciencIA.md))

</div>

## ¿Para qué?

||||
|-|-|-|
|Entender que un LLM no razona: predice secuencias.|Experimentar en primera persona sus aciertos y fallos, y clasificar sus causas.|Conocer algunas técnicas de prompting y aplicarlas.|

Este taller busca evidenciar esa confianza ciega y reconstruirla sobre una base técnica.

## ¿Cómo?

### ¿Qué pueden hacer?

¿Propuestas?

<div align=center>

<table>
<tr><th>¿Pueden ver?</th><th>¿Y los idiomas?</th><th>¿Programación?</th></tr>
<tr><td valign=top>
<details>
<summary></summary>

[CdU de visión](https://github.com/mmasias/ai-prompts/blob/main/documentos/casosDeUso/visionGPT.md)

Tareas que explotan la capacidad multimodal de los LLMs: reciben una imagen y generan texto a partir de ella (descripción, transcripción, análisis, sugerencias).
</details>
</td><td valign=top>
<details>
<summary></summary>

[CdU de traducción](https://github.com/mmasias/u6-VII-traslation-project)

Traducción de los diálogos [del remake de un videojuego clásico (Ultima VI)](https://ultima6.ultimacodex.com/the-ultima-6-remake/) al español, adaptando el registro lingüístico al personaje: un pirata habla como pirata del Siglo de Oro, un rey habla como monarca castellano — a partir del mismo código fuente.
</details>
</td><td valign=top>
<details>
<summary></summary>

CdU de desarrollo

Generación de código funcional a partir de una descripción en lenguaje natural.
</details>
</td></tr>
</table>

</div>

### Pero... ¿pueden pensar?

- ¿Son manazas con manzanas?
  <details>
  <summary></summary>
  <ul>
    <li>La cafetería tiene 23 manzanas. Si usaron 20 para preparar un postre y compraron 6 más, ¿cuántas manzanas tienen ahora?</li>
    <li>Dame oraciones que terminen con la palabra "manzana" 
    <li>Dame oraciones donde la palabra "manzana" esté en cuarto lugar
    <li>Dame diez oraciones, donde la palabra manzana esté en la primera posición en la primera oración, en la segunda posición en la segunda oración, en la tercera posición en la tercera oración y así sucesivamente hasta llegar a la décima oración
  </ul>
  </details>
- La familia no es lo suyo
  <details>
  <summary></summary>
  <ul>
    <li>En una habitación hay 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda)? [🧾](https://chatgpt.com/share/6895e9cf-98f4-8002-bd8a-39de093981f6)
    <li>En una habitación estamos solo 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda) y qué relación tiene conmigo?
    <li>Anita tiene dos hermanos. Cada hermano tiene dos hermanas. ¿Cuántas hermanas tiene Anita?
    <li>Alicia tiene 2 hermanas y también tiene 4 hermanos. ¿Cuántas hermanas tienen los hermanos de Alicia?
  </ul>
  </details>  
- Los números como que no... Las letras, bueno...
  <details>
  <summary></summary>
  <ul>
    <li>¿Cuál es el número entero más pequeño cuyo cuadrado está entre 15 y 30? [🧾](https://github.com/mmasias/ai-prompts/blob/main/documentos/casosDeUso/acertijoMatem%C3%A1tico.md)
    <li>¿Es 9.11 > 9.9?
  </ul>
  <ul>
  <li>SACO es a ASCO lo que 7683 es a... [🧾](https://chatgpt.com/share/6895ed07-62a4-8002-a426-d9a321eb7e5f) [🧾](https://claude.ai/share/23b3b47a-c492-43a8-9b43-711350017ee0)
    </ul>
  </details>
- Cervantes en particular -y la literatura en general- les puede
  <details>
  <summary></summary>
  <ul>
    <li>Escríbeme una frase que no contenga ninguna palabra que aparezca en "El Quijote"
  </ul>
  </details>
- ¿Siguen instrucciones?
  <details>
  <summary></summary>
  <ul>
  <li>Escribe exactamente lo que te diga / murciélago al revés
    </ul>
  </details>
- La física no viene de serie
  <details>
  <summary></summary>
  <ul>
    <li>Ana pone una pelota en una caja sin tapa. Lleva la caja del garaje a la cocina. En la cocina, le pone una tapa a la caja. La voltea boca abajo. Quita la caja y con cuidado lleva la tapa al jardín. ¿Dónde está la pelota?
  </ul>
  </details>
- ¿Y si les enseñamos fotos?
  <details>
  <summary></summary>
    <li><img src="https://raw.githubusercontent.com/mmasias/ai-prompts/main/documentos/imagenes/perritos.png">
    <li> <a href="https://github.com/mmasias/ai-prompts/tree/main/documentos/imagenes/testVisuaLLM">Más imágenes</a>
  </details>
- ¿Qué tal dibujan?
  <details>
  <summary></summary>
  <li> Dibuja la esfera de un reloj, coloca los números y marca las manecillas a las nueve y diez.
  </details>
- ¿Se reconocen a sí mismas?
  <details>
  <summary></summary>
  <li> Generar una imagen
  <li> Preguntarle si es generada por AI o por un humano
  </details>

> [*Más ejemplos*](https://github.com/mmasias/ai-prompts/blob/main/documentos/casosDeUso/diversosTest.md)

### ¿Qué hacer?

Tomemos uno de los ejemplos que fallaron y [una técnica](https://github.com/mmasias/ai-prompts/blob/main/documentos/ingenieriaDePrompts/arbolPensamiento.md)

Esto es:

#### Ingeniería de prompts

<div align=center>

|Técnica|miniDefinición|Ejemplo|
|-|-|-|
|[Sesgar (formalmente "Priming")](https://github.com/mmasias/ai-prompts/blob/main/documentos/ingenieriaDePrompts/priming.md)|Preparar al modelo con contexto, rol o restricciones antes de la pregunta real.|"Actúa como profesor de física. Ahora dime: ¿dónde está la pelota?"|
|Descomposición|Partir la tarea en subtareas verificables.|"Primero escribe la palabra letra por letra. Luego cuenta las R."|
|[Few shots](https://github.com/mmasias/ai-prompts/blob/main/documentos/ingenieriaDePrompts/xShotPrompting.md)|Darle ejemplos resueltos antes de la pregunta real.|"Ejemplo: CASA→ASAC, MESA→ASEM. Ahora: SACO→ASCO, 7683→..."|
|[Cadena de pensamiento](https://github.com/mmasias/ai-prompts/blob/main/documentos/ingenieriaDePrompts/chainOfThought.md)|Forzar al modelo a razonar paso a paso antes de responder.|"Antes de responder, razona paso a paso."|
|Autoverificación|Obligar al modelo a revisar su propia respuesta.|"Resuelve esto. Luego revisa tu respuesta buscando errores."|
|[Árbol de pensamiento](https://github.com/mmasias/ai-prompts/blob/main/documentos/ingenieriaDePrompts/arbolPensamiento.md)|Hacer que varios "expertos" debatan y se corrijan entre sí.|"Imagina que tres expertos responden. Cada uno escribe un paso, lo comparten, y si alguno ve un error, se retira."|

</div>

## Y ahora, ¿qué?

Si quieren seguir explorando cosas de AI, el repo de [Pequeñas anécdotas sobre los LLMs](https://github.com/mmasias/ai-prompts) puede resultarles interesante. 

<details>
<summary><b>Eso sí...</b></summary>

<table>
<tr>
<td width=50%>
<img src="https://raw.githubusercontent.com/mmasias/ai-prompts/main/documentos/imagenes/spaceStation.png">
</td><td>

<sub>Este repositorio contiene artículos largos, detallados y que requieren lectura activa.<sub>

|<sub>No contiene|<sub>Contiene|
|-|-|
|<sub>Listas de "5 prompts mágicos"<br>Resúmenes en viñetas de 3 líneas<br>"Hacks" que prometen resultados en 30 segundos<br>Contenido viral sin sustancia|<sub>Análisis de problemas reales<br>Razonamiento detrás de cada decisión<br>Transcripciones completas del proceso<br>Reflexiones sobre qué funcionó y qué no

<sub>Y es que entender cómo pensar con IA es más valioso que memorizar prompts.
<br>- Porque los casos de uso complejos requieren contexto.
<br>- Porque si esto fuera resumible en 280 caracteres, no valdría la pena documentarlo.
<br>- Si buscas contenido "rápido y fácil" este no es tu repositorio.
<br>- Internet en general, y Linkedin y X en particular, están lleno de listas que prometen atajos.</sub>

<sub>Si quieres empezar a entender profundamente cómo trabajar con LLMs, bienvenido, ponte cómodo: vas a leer.
<div align=right><sub><i>La búsqueda del conocimiento no cabe en un tweet.</i></div>
</td>
</tr>
</table>

</details>

>  
> **Leer**. Calidad más que cantidad: [Paper](https://arxiv.org/pdf/2602.06176)
>  

## 2Think

Si no piensa pero acierta el 90%... ¿realmente importa?
