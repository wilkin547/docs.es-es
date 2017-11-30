---
title: Tipo unit (F#)
description: "Obtenga información acerca de cómo el tipo de 'unidad' F # a menudo se usa para contener el lugar donde se requiere un valor mediante la sintaxis del lenguaje cuando se es necesario o deseable ningún valor."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: eabbb6d7-80f3-4fa5-80b4-0f48982466a7
ms.openlocfilehash: 60ac08c0e3f8380a8f9dec7a083ede93c68bb0e8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="unit-type"></a>Unit (Tipo)

El `unit` es un tipo que indica la ausencia de un valor específico; el `unit` tipo tiene un único valor, que actúa como un marcador de posición cuando ningún otro valor existe o es necesario.


## <a name="syntax"></a>Sintaxis

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Comentarios
Cada expresión de F # debe evaluarse como un valor. Para las expresiones que no generan un valor que es de interés, el valor de tipo `unit` se utiliza. El `unit` tipo es similar a la `void` tipo en lenguajes como C# y C++.

El `unit` tipo tiene un solo valor y ese valor se indica mediante el token `()`.

El valor de la `unit` tipo suele utilizarse en programación para mantener la posición donde se requiere un valor mediante la sintaxis del lenguaje, pero cuando se es necesario o deseable ningún valor de F #. Un ejemplo podría ser el valor devuelto de un `printf` función. Dado que las acciones importantes de la `printf` operación se realiza en la función, la función no tiene que devolver un valor real. Por lo tanto, el valor devuelto es de tipo `unit`.

Algunas construcciones esperan un `unit` valor. Por ejemplo, un `do` enlace o en cualquier código en el nivel superior de un módulo se espera que se evalúen como un `unit` valor. El compilador emite una advertencia cuando un `do` enlace o el código en el nivel superior de un módulo genera un resultado distinto de la `unit` valor que no se utiliza, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Esta advertencia es una característica de programación funcional; no aparecen en otros lenguajes de programación. NET. En un programa puramente funcional, en el que las funciones no tienen efectos secundarios, el valor devuelto final es el único resultado de una llamada de función. Por lo tanto, cuando se omite el resultado, es un posible error de programación. Aunque F # no es un lenguaje de programación puramente funcional, es recomendable seguir el estilo de programación funcional siempre que sea posible.

## <a name="see-also"></a>Vea también
[Primitivos](primitive-types.md)

[Referencia del lenguaje F#](index.md)
