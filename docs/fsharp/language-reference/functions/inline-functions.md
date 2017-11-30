---
title: Funciones inline (F#)
description: "Obtenga información acerca de cómo usar F # en línea las funciones que se integran directamente en el código de llamada."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a>Funciones insertadas

*Funciones inline* son funciones que se integran directamente en el código de llamada.


## <a name="using-inline-functions"></a>Uso de funciones Inline
Cuando se usan parámetros de tipo estático, las funciones con parámetros de tipo deben ser funciones inline. Esto garantiza que el compilador puede resolver estos parámetros de tipo. Cuando se usan parámetros de tipo genérico normal, no hay ninguna restricción así.

Además de habilitar el uso de restricciones de miembro, funciones insertadas pueden resultar útil para optimizar el código. Sin embargo, el uso excesivo de funciones insertadas puede provocar que el código sea menos resistente a los cambios en las optimizaciones del compilador y la implementación de funciones de la biblioteca. Por esta razón, debe evitar el uso de funciones inline para la optimización, a menos que se han intentado todas las otras técnicas de optimización. Realizar una función o método en línea a veces puede mejorar el rendimiento, pero no es siempre el caso. Por lo tanto, también debe usar las medidas de rendimiento para comprobar que realizar cualquier función especificada insertada en realidad tienen un efecto positivo.

El `inline` modificador se puede aplicar a las funciones en el nivel superior, en el nivel de módulo o en el nivel de método en una clase.

En el ejemplo de código siguiente se muestra una función inline en el nivel superior, un método de instancia insertado y un método estático insertado.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a>Funciones inline e inferencia de tipo
La presencia de `inline` afecta a la inferencia de tipo. Esto es porque las funciones insertadas pueden resueltos estáticamente parámetros de tipo, mientras que no sean inline (funciones) no pueden. En el ejemplo de código siguiente se muestra un caso donde `inline` es útil porque se usa una función que tiene un parámetro de tipo resueltos estáticamente, la `float` operador de conversión.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Sin el `inline` fuerza la inferencia de tipo modificador, la función para que acepte un tipo específico, en este caso `int`. Pero con la `inline` modificador, la función también se deduce que tiene un parámetro de tipo resueltos estáticamente. Con el `inline` modificador, el tipo se deduce que la manera siguiente:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Esto significa que la función acepta cualquier tipo que admita una conversión a **float**.


## <a name="see-also"></a>Vea también
[Funciones](index.md)

[Restricciones](../generics/constraints.md)

[Parámetros de tipo resueltos estáticamente](../generics/statically-resolved-type-parameters.md)
