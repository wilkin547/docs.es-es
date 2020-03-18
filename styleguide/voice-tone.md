---
ms.openlocfilehash: 2692a83ff351557889d4d573b6f7cddfe6739983
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72523948"
---
# <a name="voice-and-tone-guidelines"></a>Instrucciones de voz y tono

Una gran variedad de personas, incluidos profesionales de TI y desarrolladores, leen tus documentos tanto para aprender .NET como para usarlo en su trabajo habitual.
Tu objetivo es crear documentación útil que ayude al lector en su trabajo. Nuestras instrucciones proporcionan ayuda en esa labor. La guía de estilo incluye las recomendaciones siguientes:

- [Utiliza un tono de conversación](#use-a-conversational-tone)
- [Escribe en segunda persona](#write-in-2nd-person)
- [Utiliza la voz activa](#use-active-voice)
- [Escribe para un nivel de lectura de 5º de primaria](#target-a-fifth-grade-reading-level)
- [Evita el tiempo verbal futuro](#avoid-future-tense)
- [¿Qué es? ¿Y qué?](#what-is-it-so-what)

Puedes ver ejemplos de cada una de ellas conforme leas esta guía de estilo. Hemos escrito esta guía siguiendo nuestras directrices para proporcionar ejemplos que debes seguir al crear documentación para .NET Core. También se incluyen ejemplos contrastados para que puedas ver el aspecto de los artículos cuando no se siguen nuestras directrices.

## <a name="details-on-each-guideline"></a>Más información sobre cada directriz

### <a name="use-a-conversational-tone"></a>Utiliza un tono de conversación

#### <a name="appropriate-style"></a>Estilo apropiado:

Queremos que nuestra documentación tenga un tono de conversación. Debería dar la impresión de que estás teniendo una conversación con el autor conforme lees cualquiera de nuestros tutoriales o explicaciones.
Para ti, la experiencia debe ser informal, con tono de conversación e informativa. Los lectores de deben sentir como si estuvieran escuchando al autor explicar los conceptos.

#### <a name="inappropriate-style"></a>Estilo inapropiado:

Es posible ver la diferencia entre un estilo de conversación y el estilo que se encuentra con tratamientos más académicos de temas técnicos. Estos recursos son muy útiles, pero los autores han escrito esos artículos en un estilo muy diferente al de nuestra documentación. Al leer una publicación académica, encontramos un tono muy diferente y un estilo de escritura muy distinto.
Los lectores sienten que están leyendo un relato aburrido de un tema muy aburrido.

El primer párrafo anterior sigue nuestro estilo de conversación recomendado. El segundo tiene un estilo más académico. Es posible ver la diferencia inmediatamente.

### <a name="write-in-second-person"></a>Escribir en segunda persona

#### <a name="appropriate-style"></a>Estilo apropiado:

Debes escribir tus artículos como si hablaras directamente con el lector. Debes usar la segunda persona con frecuencia (que acabo de hacer en estas dos oraciones). La segunda persona no siempre significa el uso de la palabra 'tú'. Escribe directamente al lector. Escribe oraciones imperativas.
Indica al lector lo que deseas que aprendan.

#### <a name="inappropriate-style"></a>Estilo inapropiado:

Un autor también podría optar por escribir en tercera persona. En este modelo, un autor debe buscar algunos pronombres o sustantivos para utilizar al hacer referencia al lector. A menudo, un lector puede encontrar que este estilo de tercera persona es menos atractivo y menos agradable a leer.

El primer párrafo sigue nuestro estilo recomendado. El segundo usa la tercera persona. Escribe en segunda persona. Probablemente te resultará más fácil leerlo.

### <a name="use-active-voice"></a>Utilizar la voz activa

Escribe tus artículos en voz activa. Voz activa significa que el sujeto de la oración realiza la acción (verbo) de esa oración. Compárala con la voz pasiva, en la que se organiza la oración de forma que se el sujeto de la oración padece la acción. Compara estos dos ejemplos:

>El compilador transforma el código fuente en un archivo ejecutable.

>El código fuente ha sido transformado por el compilador en un archivo ejecutable.

La primera oración utiliza voz activa. La segunda oración está escrita en voz pasiva.
(Estas dos oraciones proporcionan otro ejemplo de cada estilo).

Se recomienda la voz activa porque es más legible. La voz pasiva puede ser más difícil de leer.

### <a name="target-a-fifth-grade-reading-level"></a>Escribir para un nivel de lectura de 5º de primaria

Proporcionamos esta directriz final porque muchos de nuestros lectores no son hablantes nativos de inglés.
Estás llegando a un público internacional con tus artículos. Ten en cuenta que es posible que no tenga el vocabulario en inglés que tu posees.

Sin embargo, también escribes para profesionales técnicos. Se puede suponer que los lectores tienen conocimientos de programación y el vocabulario de términos de programación específico. Programación orientada a objetos, clase y objeto, función y método serán términos conocidos. Sin embargo, no todos los usuarios que leen los artículos tienen una carrera en informática. Probablemente deberás definir términos como 'idempotente' si los utilizas:

> El método Close() es idempotente, lo que significa que se puede llamar varias veces y el efecto es el mismo que si se llamase una vez.

### <a name="avoid-future-tense"></a>Evita el tiempo verbal futuro

En ciertos idiomas distintos del inglés, el concepto del tiempo verbal futuro no es igual que en inglés. Usar el futuro puede hacer que sea más difícil leer los documentos. Además, cuando se usa el futuro, la pregunta obvia es "¿Cuándo?". Por lo tanto, si dices "Aprender PowerShell será bueno para ti", la pregunta obvia para el lector es "¿Cuándo será bueno?". En vez de eso, simplemente tienes que decir "Aprender PowerShell es bueno para ti".

### <a name="what-is-it---so-what"></a>¿Qué es? ¿Y qué?

Siempre que presentes un concepto nuevo al lector, defínelo y solo entonces explica por qué es útil. Es importante que el lector entienda qué es algo antes de que pueda entender las ventajas que tiene.
