---
title: Expresiones con procesamiento diferido (F#)
description: "Obtenga información acerca de cómo F # con procesamiento diferido puede mejorar el rendimiento de sus aplicaciones y bibliotecas."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3499293e-1d53-4b02-b764-f687fbdaa7fe
ms.openlocfilehash: 984c96ab68a8919e2382eefe8260b07f191027dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="lazy-computations"></a>Expresiones con procesamiento diferido

*Expresiones con procesamiento diferidas* son cálculos que no se evalúan inmediatamente, pero en su lugar se evalúan cuando se necesita el resultado. Esto puede ayudar a mejorar el rendimiento del código.

## <a name="syntax"></a>Sintaxis

```fsharp
let identifier = lazy ( expression )
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *expresión* es código que se evalúa solo cuando sea necesario, un resultado y *identificador* es un valor que almacena el resultado. El valor es de tipo [ `Lazy<'T>` ](https://msdn.microsoft.com/library/b29d0af5-6efb-4a55-a278-2662a4ecc489), donde el tipo real que se utiliza para `'T` se determina a partir del resultado de la expresión.

Expresiones con procesamiento diferidas permiten mejorar el rendimiento mediante la restricción de la ejecución de un cálculo a solo aquellas situaciones en que se necesita un resultado.

Para forzar el cálculo que se realice, llame al método `Force`. `Force`hace que la ejecución realizar solo una vez. Las llamadas subsiguientes a `Force` devuelven el mismo resultado, pero no ejecute ningún código.

El código siguiente muestra el uso de expresiones con procesamiento diferido y el uso de `Force`. En este código, el tipo de `result` es `Lazy<int>`y el `Force` método devuelve un `int`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet73011.fs)]

La evaluación diferida, pero no el `Lazy` escriba, también se utiliza para las secuencias. Para obtener más información, consulte [secuencias](sequences.md).

## <a name="see-also"></a>Vea también

[Referencia del lenguaje F#](index.md)

[LazyExtensions (módulo)](https://msdn.microsoft.com/library/86671f40-84a0-402a-867d-ae596218d948)
