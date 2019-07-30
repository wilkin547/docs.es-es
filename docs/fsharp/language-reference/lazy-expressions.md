---
title: Expresiones diferidas
description: Obtenga información F# sobre cómo las expresiones diferidas pueden mejorar el rendimiento de las aplicaciones y las bibliotecas.
ms.date: 03/13/2019
ms.openlocfilehash: 97429e9a4c3838cbaa2ead197db4443e0820e8b3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630739"
---
# <a name="lazy-expressions"></a>Expresiones diferidas

Las *expresiones diferidas* son expresiones que no se evalúan inmediatamente, pero se evalúan en su lugar cuando se necesita el resultado. Esto puede ayudar a mejorar el rendimiento del código.

## <a name="syntax"></a>Sintaxis

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *Expression* es un código que solo se evalúa cuando se requiere un resultado y *Identifier* es un valor que almacena el resultado. El valor es de tipo [`Lazy<'T>`](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.

Las expresiones diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de una expresión a solo aquellas situaciones en las que se necesita un resultado.

Para forzar que se realicen las expresiones, llame al `Force`método. `Force`hace que la ejecución se realice solo una vez. Las siguientes llamadas `Force` a devuelven el mismo resultado, pero no ejecutan ningún código.

En el código siguiente se muestra el uso de expresiones diferidas y el `Force`uso de. En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La evaluación diferida, pero `Lazy` no el tipo, también se usa para las secuencias. Para obtener más información, vea [secuencias](sequences.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Módulo LazyExtensions](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
