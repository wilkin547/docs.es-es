---
title: Expresiones con procesamiento diferido (F#)
description: 'Obtenga información sobre cómo F # con procesamiento diferido puede mejorar el rendimiento de las aplicaciones y bibliotecas.'
ms.date: 05/16/2016
ms.openlocfilehash: 8afe815f26978de96291a52973d54a9dbcc5eaf2
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698215"
---
# <a name="lazy-computations"></a>Expresiones con procesamiento diferido

*Expresiones con procesamiento diferidas* son cálculos que no se evaluarán inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado. Esto puede ayudar a mejorar el rendimiento del código.

## <a name="syntax"></a>Sintaxis

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *expresión* es código que se evalúa solo cuando es necesario, un resultado y *identificador* es un valor que almacena el resultado. El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se usa para `'T` se determina a partir del resultado de la expresión.

Expresiones con procesamiento diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de un cálculo a sólo aquellas situaciones en que se necesita un resultado.

Para forzar que se puede realizar el cálculo, se llama al método `Force`. `Force` hace que la ejecución se realiza solo una vez. Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.

El código siguiente ilustra el uso de la expresión con procesamiento diferido y el uso de `Force`. En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La evaluación diferida, pero no la `Lazy` escriba, también se usa para las secuencias. Para obtener más información, consulte [secuencias](sequences.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [LazyExtensions (módulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
