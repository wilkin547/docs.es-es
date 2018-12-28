---
title: Inferencia de tipos
description: Obtenga información sobre cómo el F# compilador infiere los tipos de valores, variables, parámetros y valores devueltos.
ms.date: 05/16/2016
ms.openlocfilehash: 3e61d5c81fde0a48af66a47745123a842dc04cb1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612795"
---
# <a name="type-inference"></a>Inferencia de tipos

Este tema se describe cómo el F# compilador infiere los tipos de valores, variables, parámetros y valores devueltos.

## <a name="type-inference-in-general"></a>Inferencia de tipos en General

La idea de inferencia de tipos es que no es necesario especificar los tipos de F# construcciones excepto cuando el compilador de forma concluyente no puede deducir el tipo. Omitir información de tipo explícita no significa que F# es un lenguaje dinámico o que los valores de F# son débilmente tipado. F#es un lenguaje de tipo estático, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación. Si no hay información suficiente para que el compilador deduzca los tipos de cada construcción, debe proporcionar información adicional de tipo, normalmente mediante la adición de anotaciones de tipo explícitas en algún lugar en el código.

## <a name="inference-of-parameter-and-return-types"></a>Inferencia de parámetro y tipos de valor devuelto

En una lista de parámetros, no es necesario especificar el tipo de cada parámetro. Y aún, F# es un lenguaje de tipo estático y, por lo tanto, cada valor y expresión tiene un tipo definido en tiempo de compilación. Para esos tipos que no se especifique explícitamente, el compilador deduce el tipo según el contexto. Si el tipo no es lo contrario especificado, se deduce para ser genérico. Si el código usa un valor de forma incoherente, de tal manera que no es único no puede inferir tipo que cumpla todos los usos de un valor, que el compilador notifica un error.

El tipo de valor devuelto de una función viene determinada por el tipo de la última expresión en la función.

Por ejemplo, en el código siguiente, los tipos de parámetro `a` y `b` y el tipo de valor devuelto se infiere para ser `int` porque el literal `100` es de tipo `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Puede influir en la inferencia de tipo cambiando los literales. Si realiza la `100` un `uint32` anexando el sufijo `u`, los tipos de `a`, `b`, y el valor devuelto se infiere para ser `uint32`.

También puede influir en inferencia de tipos mediante el uso de otras construcciones que implican restricciones sobre el tipo, como las funciones y métodos que funcionan con solo un tipo determinado.

Además, puede aplicar anotaciones de tipo explícitas a parámetros de función o un método o a variables en expresiones, como se muestra en los ejemplos siguientes. Producir un error si se producen conflictos entre las distintas restricciones.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de todo los parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso común donde es útil en un parámetro de una anotación de tipo es cuando el parámetro es un tipo de objeto y desea usar a un miembro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a>Generalización automática

Si el código de función no es depende del tipo de un parámetro, el compilador considera que el parámetro es genérico. Esto se denomina *generalización automática*, y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.

Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

El tipo se infiere para ser

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Información adicional

Inferencia de tipos se describe con más detalle en la F# especificación del lenguaje.

## <a name="see-also"></a>Vea también

- [Generalización automática](generics/automatic-generalization.md)