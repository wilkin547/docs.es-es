---
title: Inferencia de tipos (F#)
description: 'Obtenga información acerca de cómo el compilador de F # infiere los tipos de valores, variables, parámetros y valores devueltos.'
ms.date: 05/16/2016
ms.openlocfilehash: 93e1568ebe71436ad8f7119ac9d9628cdf58012a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="type-inference"></a>Inferencia de tipos

Este tema describe cómo el compilador de F # infiere los tipos de valores, variables, parámetros y valores devueltos.

## <a name="type-inference-in-general"></a>Inferencia de tipos en General
La idea de inferencia de tipos es que no es necesario especificar los tipos de construcciones de F # excepto cuando el compilador no puede deducir de forma concluyente el tipo. Omisión de información de tipos explícita no significa que F # es un lenguaje con tipos dinámicos o que los valores de F # estén débilmente tipados. F # es un lenguaje de tipos estáticos, lo que significa que el compilador deduce un tipo exacto para cada construcción durante la compilación. Si no hay suficiente información para que el compilador deduzca los tipos de cada construcción, debe proporcionar información adicional sobre tipos, normalmente mediante la adición de anotaciones de tipo explícitas en alguna parte en el código.


## <a name="inference-of-parameter-and-return-types"></a>Inferencia de parámetro y tipos de valor devuelto
En una lista de parámetros, no es necesario especificar el tipo de cada parámetro. Sin embargo, F # es un lenguaje con tipos estáticos y, por tanto, cada valor y expresión tiene un tipo definido en tiempo de compilación. Para los tipos que no se especifique explícitamente, el compilador deduce el tipo en función del contexto. Si el tipo no es lo contrario especificado, se deduce para ser genérico. Si el código utiliza un valor de forma incoherente, de tal forma que hay no único tipo deducido que satisfaga todos los usos de un valor, que el compilador informa de un error.

El tipo de valor devuelto de una función está determinado por el tipo de la última expresión de la función.

Por ejemplo, en el código siguiente, los tipos de parámetro `a` y `b` y el tipo de valor devuelto se deducen como `int` porque el literal `100` es de tipo `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

Puede influir en la inferencia de tipo cambiando los literales. Si realiza la `100` una `uint32` anexando el sufijo `u`, los tipos de `a`, `b`, y el valor devuelto se deducen como `uint32`.

También puede influir en inferencia de tipos utilizando otras construcciones que impliquen restricciones sobre el tipo, como las funciones y métodos que funcionan con solo un tipo determinado.

Además, puede aplicar anotaciones de tipo explícitas a los parámetros de función o un método o a las variables en las expresiones, como se muestra en los ejemplos siguientes. Producir un error si se producen conflictos entre diferentes restricciones.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

Puede especificar explícitamente el valor devuelto de una función proporcionando una anotación de tipo después de que todos los parámetros.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

Un caso común donde es útil en un parámetro de una anotación de tipo es cuando el parámetro es un tipo de objeto y desea usar a un miembro.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]
    
## <a name="automatic-generalization"></a>Generalización automática
Si el código de función no es depende del tipo de un parámetro, el compilador considera que el parámetro para ser genérico. Esto se denomina *generalización automática*, y puede ser una ayuda eficaz para escribir código genérico sin aumentar la complejidad.

Por ejemplo, la función siguiente combina dos parámetros de cualquier tipo en una tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

El tipo se deduce como

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a>Información adicional
Inferencia de tipo se describe con más detalle en la especificación del lenguaje F #.


## <a name="see-also"></a>Vea también
[Generalización automática](generics/automatic-generalization.md)
