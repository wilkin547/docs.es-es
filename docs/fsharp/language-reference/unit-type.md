---
title: Tipo unit (F#)
description: 'Obtenga información sobre cómo el tipo de F # "unit" a menudo se usa para contener el lugar donde se requiere un valor mediante la sintaxis del lenguaje cuando se necesita ningún valor o se desea.'
ms.date: 05/16/2016
ms.openlocfilehash: c3dfa5f63c25a1e8abc0f75b905c129b311479af
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44097157"
---
# <a name="unit-type"></a>Unit (Tipo)

El `unit` tipo es un tipo que indica la ausencia de un valor específico; el `unit` tipo tiene un solo valor, que actúa como un marcador de posición cuando ningún otro valor existe o es necesario.

## <a name="syntax"></a>Sintaxis

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Comentarios

Cada expresión de F # debe evaluarse como un valor. Para las expresiones que no generan un valor que es de interés, el valor de tipo `unit` se utiliza. El `unit` tipo es similar a la `void` tipo en lenguajes como C# y C++.

El `unit` tipo tiene un valor único, y ese valor se indica mediante el token `()`.

El valor de la `unit` a menudo se usa el tipo en F #, programación para mantener la posición donde se requiere un valor mediante la sintaxis del lenguaje, pero cuando se necesita ningún valor o se desea. Un ejemplo podría ser el valor devuelto de un `printf` función. Dado que las acciones importantes de la `printf` operación se producen en la función, la función no tiene que devolver un valor real. Por lo tanto, el valor devuelto es de tipo `unit`.

Algunas construcciones esperan un `unit` valor. Por ejemplo, un `do` enlace o cualquier código en el nivel superior de un módulo que se espera que se evalúan como un `unit` valor. El compilador emite una advertencia cuando un `do` enlace o código en el nivel superior de un módulo genera un resultado distinto el `unit` valor que no se usa, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Esta advertencia es una característica de programación funcional; no aparecen en otros lenguajes de programación. NET. En un programa puramente funcional, en el que las funciones no tienen efectos secundarios, el valor devuelto final es el único resultado de una llamada de función. Por lo tanto, cuando se omite el resultado es un posible error de programación. Aunque F # no es un lenguaje de programación puramente funcional, es conveniente seguir el estilo de programación funcional, siempre que sea posible.

## <a name="see-also"></a>Vea también

- [Primitivos](primitive-types.md)
- [Referencia del lenguaje F#](index.md)
