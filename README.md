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

|[![](https://img.shields.io/badge/-ChatGPT-FFF?style=flat&logo=openai&logoColor=black)](https://chat.openai.com/) [![](https://img.shields.io/badge/-Claude-FFF?style=flat&logo=anthropic&logoColor=black)](https://claude.ai/chats) [![](https://img.shields.io/badge/-Gemini-FFF?style=flat&logo=googlegemini&logoColor=black)](https://gemini.google.com/app) [![](https://img.shields.io/badge/-DeepSeek-FFF?style=flat&logo=deepseek&logoColor=black)](https://chat.deepseek.com/) [![](https://img.shields.io/badge/-Grok-FFF?style=flat&logo=x&logoColor=black)](https://x.com/i/grok) [![](https://img.shields.io/badge/-MetaAI-FFF?style=flat&logo=meta&logoColor=black)](https://www.meta.ai/) [![](https://img.shields.io/badge/-Copilot-FFF?style=flat&logo=microsoft&logoColor=black)](https://copilot.microsoft.com/)<br>[![](https://img.shields.io/badge/-Perplexity-FFF?style=flat&logo=perplexity&logoColor=black)](https://www.perplexity.ai/) [![](https://img.shields.io/badge/-Mistral-FFF?style=flat)](https://chat.mistral.ai/chat) [![](https://img.shields.io/badge/-Qwen-FFF?style=flat&logo=qwen&logoColor=black)](https://chat.qwen.ai/) [![](https://img.shields.io/badge/-Neuroflash-FFF?style=flat&logo=&logoColor=black)](https://app.neuro-flash.com/aiWriter) [![](https://img.shields.io/badge/-Huggingface-FFF?style=flat&logo=&logoColor=black)](https://huggingface.co/chat)
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
    <li>En una habitación hay 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda)?
    <li>En una habitación estamos solo 3 hermanas: Anna está leyendo un libro. Alice está jugando una partida de ajedrez. ¿Qué está haciendo la tercera persona (llamada Amanda) y qué relación tiene conmigo?
    <li>Anita tiene dos hermanos. Cada hermano tiene dos hermanas. ¿Cuántas hermanas tiene Anita?
    <li>Alicia tiene 2 hermanas y también tiene 4 hermanos. ¿Cuántas hermanas tienen los hermanos de Alicia?
  </ul>
  </details>  
- Los números como que no...
  <details>
  <summary></summary>
  <ul>
    <li>¿Cuál es el número entero más pequeño cuyo cuadrado está entre 15 y 30?
  </ul>
  </details>
- ¿Serán de letras?
  <details>
  <summary></summary>
  <ul>
  <li>SACO es a ASCO lo que 7683 es a...
    </ul>
  </details>
- Cervantes en particular -y la literatura en general- les puede
  <details>
  <summary></summary>
  <ul>
    <li>Escríbeme una frase que no contenga ninguna palabra que aparezca en "El Quijote"
  </ul>
  </details>