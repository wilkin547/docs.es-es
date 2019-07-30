---
title: Inferencia de tipos
description: Obtenga información sobre F# cómo el compilador deduce los tipos de valores, variables, parámetros y valores devueltos.
ms.date: 05/16/2016
ms.openlocfilehash: 4b18c1a67a8b7ddadb4fb334ea4736e9fd29feb0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630187"
---
# <a name="type-inference"></a>Inferencia de tipos

En este tema se describe F# cómo el compilador deduce los tipos de valores, variables, parámetros y valores devueltos.

## <a name="type-inference-in-general"></a>Inferencia de tipos en general

La idea de la inferencia de tipos es que no es necesario especificar los tipos de F# construcciones excepto cuando el compilador no puede deducir el tipo de forma concluyente. Omitir la información de tipo explícita no F# significa que se trata de un lenguaje con establecimiento dinámico de F# tipos o que los valores de están débilmente tipados. F#es un lenguaje de tipo estático, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación. Si no hay información suficiente para que el compilador deduzca los tipos de cada construcción, debe proporcionar información de tipo adicional, normalmente agregando anotaciones de tipo explícito en algún lugar del código.

## <a name="inference-of-parameter-and-return-types"></a>Inferencia de tipos de parámetro y de valor devuelto

En una lista de parámetros, no es necesario especificar el tipo de cada parámetro. Y, sin F# embargo, es un lenguaje de tipos estáticos y, por tanto, cada valor y expresión tiene un tipo definito en tiempo de compilación. En el caso de los tipos que no se especifican de forma explícita, el compilador deduce el tipo basándose en el contexto. Si el tipo no se especifica de otra forma, se deduce que es genérico. Si el código usa un valor de manera incoherente, de tal forma que no hay ningún tipo inferido único que cumpla todos los usos de un valor, el compilador informa de un error.

El tipo de valor devuelto de una función viene determinado por el tipo de la última expresión de la función.

Por ejemplo, en el código siguiente, se infiere `a` que `b` `int` los tipos de parámetro y y el tipo de valor devuelto son `100` porque el literal `int`es de tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Puede influir en la inferencia de tipos cambiando los literales. `100` Si realiza la `uint32` adición del sufijo `u`, los tipos de `a` `b`, y el valor devuelto se deducen a. `uint32`

También puede influir en la inferencia de tipos mediante el uso de otras construcciones que impliquen restricciones en el tipo, como funciones y métodos que funcionan solo con un tipo determinado.

Además, puede aplicar anotaciones de tipo explícitos a parámetros de función o de método o a variables en expresiones, tal como se muestra en los ejemplos siguientes. Se producirán errores si se producen conflictos entre las distintas restricciones.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

También puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de todos los parámetros.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso común en el que una anotación de tipo es útil en un parámetro es cuando el parámetro es un tipo de objeto y se desea usar un miembro.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Generalización automática

Si el código de la función no depende del tipo de un parámetro, el compilador considera que el parámetro es genérico. Esto se denomina *generalización automática*y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.

Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

Se deduce que el tipo es

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Información adicional

La inferencia de tipos se describe con más detalle F# en la especificación del lenguaje.

## <a name="see-also"></a>Vea también

- [Generalización automática](./generics/automatic-generalization.md)
