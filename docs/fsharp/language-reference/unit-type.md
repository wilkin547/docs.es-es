---
title: Unit (Tipo)
description: Obtenga información sobre F# cómo el tipo ' Unit ' se usa a menudo para contener el lugar en el que la sintaxis del lenguaje requiere un valor cuando no se necesita ningún valor o se desea.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424033"
---
# <a name="unit-type"></a>Unit (Tipo)

El tipo de `unit` es un tipo que indica la ausencia de un valor concreto; el tipo de `unit` solo tiene un valor único, que actúa como marcador de posición cuando no existe ningún otro valor o es necesario.

## <a name="syntax"></a>Sintaxis

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Comentarios

Cada F# expresión debe evaluarse como un valor. En el caso de las expresiones que no generan un valor de interés, se utiliza el valor de tipo `unit`. El tipo de `unit` se parece al tipo de `void` en C# lenguajes C++como y.

El tipo de `unit` tiene un valor único y ese valor se indica mediante el token `()`.

El valor del tipo de `unit` se usa a menudo F# en la programación para contener el lugar donde se requiere un valor en la sintaxis del lenguaje, pero cuando no se necesita ningún valor o no se desea. Un ejemplo podría ser el valor devuelto de una función `printf`. Dado que las acciones importantes de la operación de `printf` se producen en la función, la función no tiene que devolver un valor real. Por lo tanto, el valor devuelto es de tipo `unit`.

Algunas construcciones esperan un valor `unit`. Por ejemplo, se espera que un enlace de `do` o cualquier código en el nivel superior de un módulo se evalúe como un valor de `unit`. El compilador emite una advertencia cuando una `do` enlace o código en el nivel superior de un módulo produce un resultado distinto del valor de `unit` que no se utiliza, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Esta advertencia es una característica de la programación funcional; no aparece en otros lenguajes de programación de .NET. En un programa puramente funcional, en el que las funciones no tienen ningún efecto secundario, el valor devuelto final es el único resultado de una llamada de función. Por lo tanto, cuando se omite el resultado, es posible que se produzca un error de programación. Aunque F# no es un lenguaje de programación puramente funcional, se recomienda seguir el estilo de programación funcional siempre que sea posible.

## <a name="see-also"></a>Vea también

- [Rectangle](basic-types.md)
- [Referencia del lenguaje F#](index.md)
