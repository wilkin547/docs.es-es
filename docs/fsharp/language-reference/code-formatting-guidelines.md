---
title: "Instrucciones de formato de código (F#)"
description: "Obtenga información acerca de las instrucciones de formato de sangría de código para el lenguaje de programación para mejorar la legibilidad, la estética, la normalización y la compilación de F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3f79717c-f84e-448d-9ce4-90e40a644ba1
ms.openlocfilehash: cc56c67f356b99defd8dc28770f87be1f58443c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="code-formatting-guidelines"></a>Instrucciones de formato de código

En este tema se resume las instrucciones de sangría del código de F #. Dado que el lenguaje F # es sensible a los saltos de línea y sangría, no es simplemente un problema de legibilidad, problema estético o codificación problema de normalización para aplicar formato al código correctamente. Debe aplicar formato al código correctamente para que se compile correctamente.


## <a name="general-rules-for-indentation"></a>Reglas generales para la sangría
Cuando es necesario aplicar sangría, debe usar espacios, no tabulaciones. Se requiere al menos un espacio. Su organización puede crear los estándares de codificación para especificar el número de espacios que se utilizarán para la sangría; es típico de tres o cuatro espacios de sangría en cada nivel donde se produce la sangría. Puede configurar Visual Studio para que coincida con las normas de sangría de su organización cambiando las opciones de la `Options` cuadro de diálogo, que está disponible en la `Tools` menú. En el `Text Editor` nodo, expanda `F#` y, a continuación, haga clic en `Tabs`. Para obtener una descripción de las opciones disponibles, consulte [opciones, Editor de texto, todos los lenguajes, pestañas](https://msdn.microsoft.com/library/7sffa753.aspx).

En general, cuando el compilador analiza el código, mantiene una pila interna que indica el nivel de anidamiento actual. Cuando se aplica sangría al código, un nuevo nivel de anidamiento se crea o se inserta en la pila interna. Cuando una construcción finaliza, se extrae el nivel. La sangría es una manera de indicar el final de un nivel y sacar la pila interna, pero algunos tokens provocar también el nivel sacar, como la `end` de palabra clave, o una llave de cierre o un paréntesis.

Definición de función, el código de una construcción de varias líneas, como una definición de tipo, `try...with` construcción, construcciones de bucle y, se deben aplicar sangría con respecto a la línea de apertura de la construcción. La primera línea con sangría, Establece la posición de una columna para el código subsiguiente en la misma construcción. El nivel de sangría se denomina un *contexto*. La posición de la columna establece una columna mínima, que se conoce como un *línea de contexto*, para las líneas de código siguientes que se encuentran en el mismo contexto. Cuando se encuentra una línea de código que tiene menos sangría que esta posición de columna establecida, el compilador supone que el contexto ha finalizado y que ahora escribe código en el siguiente nivel hacia arriba, en el contexto anterior. El término *fuera de contexto* se utiliza para describir la condición en la que una línea de código desencadena el final de una construcción porque lo suficientemente alejado no se aplica una sangría. En otras palabras, el código a la izquierda de una línea de contexto está fuera de contexto. En el código con sangría correctamente, sacar partido de la regla de fuera de contexto para delinear el final de las construcciones. Si usas sangría incorrectamente, una condición de contexto puede hacer que el compilador emita una advertencia o puede dar lugar a la interpretación incorrecta de su código.

Líneas de contexto se determinan como se indica a continuación.


- Un `=` token de cancelación asociado con un `let` presenta una línea de contexto en la columna del primer token después de la `=` inicio de sesión.


- En un `if...then...else` expresión, la posición de la columna del primer token después de la `then` palabra clave o el `else` palabra clave presenta una línea de contexto.


- En un `try...with` expresión, el primer token después `try` presenta una línea de contexto.


- En un `match` expresión, el primer token después `with` y el primer token después de cada uno `->` introducen líneas de contexto.


- El primer token después `with` en un tipo de extensión presenta una línea de contexto.


- El primer token después de una llave de apertura o paréntesis o después de la `begin` de palabra clave, presenta una línea de contexto.


- El primer carácter de las palabras clave `let`, `if`, y `module` introducen líneas de contexto.


Los ejemplos de código siguiente muestran las reglas de sangría. En este caso, las instrucciones de impresión se basan en la sangría para asociarlos con el contexto adecuado. Cada vez que se desplaza a la sangría, el contexto se extrae y devuelve al contexto anterior. Por lo tanto, se imprime un espacio al final de cada iteración; "Listo". solo se imprime una vez porque la sangría fuera de contexto establece que no es parte del bucle. La impresión de la cadena "Top-Level context" no forma parte de la función. Por lo tanto, se imprime en primer lugar, durante la inicialización estática, antes de llama a la función.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

La salida es la siguiente.

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

Cuando se interrumpe las líneas largas, la continuación de la línea debe tener más sangría la construcción envolvente. Por ejemplo, los argumentos de función deben tener más sangría el primer carácter del nombre de función, como se muestra en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

Existen excepciones a estas reglas, tal como se describe en la sección siguiente.


## <a name="indentation-in-modules"></a>Sangría en los módulos
Código en un módulo local se debe aplicar la sangría en relación con el módulo, pero no es necesario que el código en un módulo de nivel superior se aplique sangría. Elementos de Namespace no es necesario que tenga la sangría.

Ejemplos de código siguientes ilustran esto.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

Para obtener más información, consulte [módulos](modules.md).


## <a name="exceptions-to-the-basic-indentation-rules"></a>Excepciones a las reglas de sangría básicas
La regla general, como se describe en la sección anterior, es que se debe aplicar sangría código construcciones de varias líneas en relación con la sangría de la primera línea de la construcción, y que el final de la construcción viene determinado por cuando se produce la primera línea de contexto. Una excepción a la regla acerca de la finalización de contextos que algunas construcciones, como el `try...with` expresión, el `if...then...else` expresión y el uso de `and` sintaxis para declarar mutuamente funciones recursivas o tipos, tienen varias partes. Aplica sangría a las partes de una versión posterior, como `then` y `else` en un `if...then...else` expresión, en el mismo nivel que el token que inicia la expresión, pero en lugar de indicar un final del contexto, representa la siguiente parte del mismo contexto. Por lo tanto, un `if...then...else` expresión puede escribirse como en el ejemplo de código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

La excepción a la regla de fuera de contexto solo se aplica a la `then` y `else` palabras clave. Por lo tanto, aunque no es un error para aplicar sangría a la `then` y `else` aún más, no puede aplicar sangría a las líneas de código en un `then` bloque genera una advertencia. Esto se muestra en las siguientes líneas de código.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

Para el código en un `else` se aplica el bloque, una regla especial adicional. Se produce la advertencia en el ejemplo anterior solo en el código en el `then` bloque, no en el código en el `else` bloque. Esto le permite escribir código que comprueba si hay varias condiciones al principio de una función sin forzar el resto del código de la función, que podría estar en un `else` bloque, que se aplique sangría. Por lo tanto, puede escribir lo siguiente sin generar una advertencia.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

Otro tipo de excepción a la regla que los contextos finalizan cuando una línea no se aplica ninguna sangría como una línea anterior es para los operadores de infijo, como `+` y `|>`. Líneas que comienzan con los operadores de infijo tienen permiso para iniciar `(1 + oplength)` columnas antes de la posición normal sin desencadenar un final del contexto, donde `oplength` es el número de caracteres que componen el operador. Esto hace que el primer token después del operador para alinearse con la línea anterior.

Por ejemplo, en el código siguiente, la `+` símbolo se permite que dos columnas con sangría menor que la línea anterior.

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

Aunque la sangría normalmente aumenta cuanto más alto el nivel de anidamiento, hay varias construcciones en la que el compilador permite restablecer la sangría en una posición inferior de la columna.

Las construcciones que permiten restablecer la posición de columna son los siguientes:


- Cuerpos de funciones anónimas. En el código siguiente, la expresión de impresión se inicia en una posición de columna que esté situado más a la izquierda de la `fun` (palabra clave). Sin embargo, la línea no debe comenzar en una columna a la izquierda del inicio del nivel de sangría anterior (es decir, a la izquierda de la `L` en `List`).
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- Construcciones que van entre paréntesis o por `begin` y `end` en un `then` o `else` bloquear de un `if...then...else` expresión, proporciona la sangría no sea inferior a la posición de la columna de la `if` (palabra clave). Esta excepción permite un estilo de codificación en la que un paréntesis de apertura o `begin` se utiliza al final de una línea después de `then` o `else`.


- Cuerpos de módulos, clases, interfaces y estructuras delimitados por `begin...end`, `{...}`, `class...end`, o `interface...end`. Esto permite un estilo en el que puede ser la palabra clave de apertura de una definición de tipo en la misma línea que el nombre del tipo sin forzar el cuerpo entero sea más la palabra clave de apertura sangría.
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
