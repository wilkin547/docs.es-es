---
title: 'Bucles: expresión while...do'
description: Vea cómo el while... hacer expresión se utiliza para realizar la ejecución iterativa (bucle) mientras una condición de prueba especificada es true.
ms.date: 05/16/2016
ms.openlocfilehash: d2a77e0bfefe3b6b026012e6b2938ba670326bcf
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613016"
---
# <a name="loops-whiledo-expression"></a>Bucles: expresión while...do

El `while...do` expresión se utiliza para realizar la ejecución iterativa (bucle) mientras una condición de prueba especificada es true.

## <a name="syntax"></a>Sintaxis

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Comentarios

El *expresión de prueba* se evalúa; si es `true`, *cuerpo de expresión* se ejecuta y se vuelve a evaluar la expresión de prueba. El *cuerpo de expresión* debe tener tipo `unit`. Si la expresión de prueba es `false`, los extremos de la iteración.

El ejemplo siguiente muestra el uso de la `while...do` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

La salida del código anterior es una secuencia de números aleatorios entre 1 y 20, el último de los cuales es 10.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Puede usar `while...do` en las expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `while...do` se usa la expresión. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Bucles: `for...in` Expresión](loops-for-in-expression.md)
- [Bucles: `for...to` Expresión](loops-for-to-expression.md)