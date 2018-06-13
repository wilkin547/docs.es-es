---
title: 'Bucles: expresión while...do (F#)'
description: Vea cómo el while... hacer expresión se utiliza para realizar la ejecución reiterativa (bucle) mientras una condición de prueba especificada es true.
ms.date: 05/16/2016
ms.openlocfilehash: e3198246e44bbb11b226f04da6795f3da22626e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562237"
---
# <a name="loops-whiledo-expression"></a>Bucles: expresión while...do

El `while...do` expresión se utiliza para realizar la ejecución reiterativa (bucle) mientras una condición de prueba especificada es true.


## <a name="syntax"></a>Sintaxis

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Comentarios
El *expresión de prueba* se evalúa; si es `true`, *cuerpo de la expresión* se ejecuta y se vuelve a evaluar la expresión de prueba. El *cuerpo-expression* debe tener tipo `unit`. Si la expresión de prueba es `false`, los extremos de la iteración.

En el ejemplo siguiente se muestra el uso de la `while...do` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

La salida del código anterior es una secuencia de números aleatorios entre 1 y 20, el último de los cuales es 10.

```
13 19 8 18 16 2 10
Found a 10!
```

>[!NOTE] 
Puede usar `while...do` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `while...do` se utiliza la expresión. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Bucles: expresión `for...in`](loops-for-in-expression.md)

[Bucles: expresión `for...to`](loops-for-to-expression.md)
