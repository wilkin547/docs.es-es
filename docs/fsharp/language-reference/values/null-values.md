---
title: Valores NULL
description: Obtenga información sobre cómo usar el valor null en F# el lenguaje de programación.
ms.date: 03/22/2019
ms.openlocfilehash: 2038c0a461fec9884c51edd50c3c9f336104e30e
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630806"
---
# <a name="null-values"></a>Valores NULL

En este tema se describe cómo se utiliza el valor F#null en.

## <a name="null-value"></a>Valor null

El valor NULL no se utiliza normalmente en F# para valores o variables. Sin embargo, null aparece como un valor anómalo en determinadas situaciones. Si se define un tipo en F#, no se permite NULL como valor normal a menos que el atributo [AllowNullLiteral](https://msdn.microsoft.com/library/4f315196-f444-4cca-ba07-1176ff71eb0f) se aplique al tipo. Si un tipo se define en algún otro lenguaje de .NET, NULL es un valor posible y, al interoperar con estos tipos, el F# código podría encontrar valores NULL.

Para un tipo definido en F# y utilizado estrictamente desde F#, la única forma de crear un valor null utilizando directamente F# la biblioteca es usar unchecked [. default](https://msdn.microsoft.com/library/9ff97f2a-1bd4-4f4c-afbe-5886a74ab977) o [array. zerocreate (](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2). Sin embargo, para F# un tipo que se usa desde otros lenguajes .net, o si está usando ese tipo con una API que no está escrita F#en, como la .NET Framework, se pueden producir valores NULL.

Puede usar el `option` tipo en F# cuando pueda usar una variable de referencia con un valor null posible en otro lenguaje .net. En lugar de NULL, con un F# `option` tipo, se usa el valor `None` de la opción si no hay ningún objeto. El valor `Some(obj)` de la opción se usa con `obj` un objeto cuando hay un objeto. Para obtener más información, vea [Opciones](../options.md). Tenga en cuenta que todavía `null` puede empaquetar un valor en una opción si, para `Some x`, `x` es `null`. Por este motivo, es importante usar `None` cuando un valor es. `null`

La `null` palabra clave es una palabra clave válida F# en el lenguaje y tiene que usarlo al trabajar con .NET Framework API u otras API escritas en otro lenguaje .net. Las dos situaciones en las que podría necesitar un valor null son cuando se llama a una API de .NET y se pasa un valor NULL como argumento, y cuando se interpreta el valor devuelto o un parámetro de salida desde una llamada al método .NET.

Para pasar un valor null a un método .net, simplemente use la `null` palabra clave en el código de llamada. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Para interpretar un valor null que se obtiene de un método .NET, use la coincidencia de patrones si es posible. En el ejemplo de código siguiente se muestra cómo usar la coincidencia de `ReadLine` patrones para interpretar el valor null que se devuelve cuando intenta leer más allá del final de un flujo de entrada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Los valores NULL F# de los tipos también se pueden generar de otras maneras, como cuando se `Array.zeroCreate`usa, que `Unchecked.defaultof`llama a. Debe tener cuidado con este código para mantener encapsulados los valores NULL. En una biblioteca diseñada únicamente para F#, no es necesario comprobar si hay valores NULL en cada función. Si está escribiendo una biblioteca para interoperar con otros lenguajes de .net, es posible que tenga que agregar comprobaciones para los parámetros `ArgumentNullException`de entrada NULL y producir una C# , tal como se hace en o Visual Basic código.

Puede usar el código siguiente para comprobar si un valor arbitrario es NULL.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vea también

- [Valores](index.md)
- [Expresiones de coincidencia](../match-expressions.md)
