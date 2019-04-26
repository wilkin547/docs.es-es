---
title: Expresiones diferidas
description: Obtenga información sobre cómo F# expresiones diferidas pueden mejorar el rendimiento de las aplicaciones y bibliotecas.
ms.date: 03/13/2019
ms.openlocfilehash: 6d53d53093f4e93f53e1c956b94e2f1e4a1bbd55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61904116"
---
# <a name="lazy-expressions"></a>Expresiones diferidas

*Expresiones diferidas* son expresiones que no se evaluarán inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado. Esto puede ayudar a mejorar el rendimiento del código.

## <a name="syntax"></a>Sintaxis

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *expresión* es código que se evalúa solo cuando es necesario, un resultado y *identificador* es un valor que almacena el resultado. El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se usa para `'T` se determina a partir del resultado de la expresión.

Las expresiones diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de una expresión a sólo aquellas situaciones en que se necesita un resultado.

Para forzar las expresiones que se va a realizarse, se llama al método `Force`. `Force` hace que la ejecución se realiza solo una vez. Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.

El código siguiente ilustra el uso de expresiones diferidas y el uso de `Force`. En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La evaluación diferida, pero no la `Lazy` escriba, también se usa para las secuencias. Para obtener más información, consulte [secuencias](sequences.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [LazyExtensions (módulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
