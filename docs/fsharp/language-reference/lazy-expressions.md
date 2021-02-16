---
title: Expresiones diferidas
description: 'Obtenga información sobre cómo las expresiones de F # Lazy pueden mejorar el rendimiento de las aplicaciones y las bibliotecas.'
ms.date: 08/15/2020
ms.openlocfilehash: 0b8496467295ce6793f80c341af88bb1819f4a47
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100425508"
---
# <a name="lazy-expressions"></a>Expresiones diferidas

Las *expresiones diferidas* son expresiones que no se evalúan inmediatamente, pero se evalúan en su lugar cuando se necesita el resultado. Esto puede ayudar a mejorar el rendimiento del código.

## <a name="syntax"></a>Sintaxis

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Expression* es un código que solo se evalúa cuando se requiere un resultado y *Identifier* es un valor que almacena el resultado. El valor es de tipo `Lazy<'T>` , donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.

Las expresiones diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de una expresión a solo aquellas situaciones en las que se necesita un resultado.

Para forzar que se realicen las expresiones, llame al método `Force` . `Force` hace que la ejecución se realice solo una vez. Las siguientes llamadas a `Force` devuelven el mismo resultado, pero no ejecutan ningún código.

En el código siguiente se muestra el uso de expresiones diferidas y el uso de `Force` . En este código, el tipo de `result` es `Lazy<int>` y el `Force` método devuelve un `int` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La evaluación diferida, pero no el `Lazy` tipo, también se usa para las secuencias. Para obtener más información, vea [secuencias](sequences.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Módulo LazyExtensions](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-lazyextensions.html)
