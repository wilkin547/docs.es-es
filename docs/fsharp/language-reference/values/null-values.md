---
title: Valores NULL
description: 'Obtenga información sobre cómo usar el valor null en el lenguaje de programación F #.'
ms.date: 08/15/2020
ms.openlocfilehash: 3b2c7ebe7b8eff08f7c3e76b9715ccab1bbd5d36
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558353"
---
# <a name="null-values"></a>Valores NULL

En este tema se describe cómo se utiliza el valor null en F #.

## <a name="null-value"></a>Valor null

El valor NULL no se utiliza normalmente en F # para valores o variables. Sin embargo, null aparece como un valor anómalo en determinadas situaciones. Si se define un tipo en F #, no se permite NULL como valor normal a menos que el atributo [AllowNullLiteral](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-allownullliteralattribute.html#Value) se aplique al tipo. Si un tipo se define en algún otro lenguaje de .NET, NULL es un valor posible y, al interoperar con estos tipos, el código de F # podría encontrar valores NULL.

Para un tipo definido en F # y usado estrictamente de F #, la única forma de crear un valor null mediante la biblioteca de F # directamente es usar [Unchecked. default](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators-unchecked.html#defaultof) o [array. zerocreate (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate). Sin embargo, para un tipo de F # que se usa desde otros lenguajes .NET, o si está usando ese tipo con una API que no está escrita en F #, como la .NET Framework, se pueden producir valores NULL.

Puede usar el `option` tipo en F # cuando puede usar una variable de referencia con un posible valor null en otro lenguaje .net. En lugar de NULL, con un tipo de F # `option` , se usa el valor de la opción `None` si no hay ningún objeto. El valor de la opción se usa `Some(obj)` con un objeto `obj` cuando hay un objeto. Para obtener más información, vea [Opciones](../options.md). Tenga en cuenta que todavía puede empaquetar un `null` valor en una opción si, para `Some x` , `x` es `null` . Por este motivo, es importante usar `None` cuando un valor es `null` .

La `null` palabra clave es una palabra clave válida en el lenguaje F # y se tiene que usar cuando se trabaja con .NET Framework API u otras API escritas en otro lenguaje .net. Las dos situaciones en las que podría necesitar un valor null son cuando se llama a una API de .NET y se pasa un valor NULL como argumento, y cuando se interpreta el valor devuelto o un parámetro de salida desde una llamada al método .NET.

Para pasar un valor null a un método .NET, simplemente use la `null` palabra clave en el código de llamada. En el siguiente ejemplo código se muestra cómo hacerlo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet701.fs)]

Para interpretar un valor null que se obtiene de un método .NET, use la coincidencia de patrones si es posible. En el ejemplo de código siguiente se muestra cómo usar la coincidencia de patrones para interpretar el valor null que se devuelve `ReadLine` cuando intenta leer más allá del final de un flujo de entrada.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet702.fs)]

Los valores NULL de los tipos de F # también se pueden generar de otras maneras, como cuando se usa `Array.zeroCreate` , que llama a `Unchecked.defaultof` . Debe tener cuidado con este código para mantener encapsulados los valores NULL. En una biblioteca destinada solo a F #, no es necesario comprobar si hay valores NULL en cada función. Si está escribiendo una biblioteca para interoperar con otros lenguajes de .NET, es posible que tenga que agregar comprobaciones para los parámetros de entrada NULL y producir una `ArgumentNullException` , tal como se hace en C# o en Visual Basic código.

Puede usar el código siguiente para comprobar si un valor arbitrario es NULL.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet703.fs)]

## <a name="see-also"></a>Vea también

- [Valores](index.md)
- [Expresiones de coincidencia](../match-expressions.md)
