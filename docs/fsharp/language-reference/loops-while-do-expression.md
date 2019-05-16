---
title: 'Bucles: expresión while...do'
description: Vea cómo el while... hacer expresión se utiliza para realizar la ejecución iterativa (bucle) mientras una condición de prueba especificada es true.
ms.date: 05/16/2016
ms.openlocfilehash: 5823ace27348ff4d4397a726bf2254f8fa0ee09b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641832"
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
