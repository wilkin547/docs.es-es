---
title: Unit (Tipo)
description: Obtenga información sobre F# cómo el tipo ' Unit ' se usa a menudo para contener el lugar en el que la sintaxis del lenguaje requiere un valor cuando no se necesita ningún valor o se desea.
ms.date: 05/16/2016
ms.openlocfilehash: 4e586702324565b8dcd4f6c7e11a0e1754f89c58
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630175"
---
# <a name="unit-type"></a>Unit (Tipo)

El `unit` tipo es un tipo que indica la ausencia de un valor específico; el `unit` tipo solo tiene un valor, que actúa como marcador de posición cuando no existe ningún otro valor o es necesario.

## <a name="syntax"></a>Sintaxis

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a>Comentarios

Cada F# expresión debe evaluarse como un valor. En el caso de las expresiones que no generan un valor de interés, se utiliza el `unit` valor de tipo. El `unit` tipo es similar al `void` tipo en lenguajes como C# y C++.

El `unit` tipo tiene un valor único y ese valor se indica mediante el token `()`.

El valor del `unit` tipo se usa a menudo en F# la programación para contener el lugar en el que la sintaxis del lenguaje requiere un valor, pero cuando no se necesita ningún valor o no se desea. Un ejemplo podría ser el valor devuelto de `printf` una función. Dado que las acciones importantes de `printf` la operación se producen en la función, la función no tiene que devolver un valor real. Por lo tanto, el valor devuelto `unit`es de tipo.

Algunas construcciones esperan un `unit` valor. Por ejemplo, se `do` espera que un enlace o cualquier código en el nivel superior de un módulo se evalúe como `unit` un valor. El compilador emite una advertencia `do` cuando un enlace o código en el nivel superior de un módulo produce un resultado distinto `unit` del valor que no se utiliza, como se muestra en el ejemplo siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

Esta advertencia es una característica de la programación funcional; no aparece en otros lenguajes de programación de .NET. En un programa puramente funcional, en el que las funciones no tienen ningún efecto secundario, el valor devuelto final es el único resultado de una llamada de función. Por lo tanto, cuando se omite el resultado, es posible que se produzca un error de programación. Aunque F# no es un lenguaje de programación puramente funcional, se recomienda seguir el estilo de programación funcional siempre que sea posible.

## <a name="see-also"></a>Vea también

- [Rectangle](primitive-types.md)
- [Referencia del lenguaje F#](index.md)
