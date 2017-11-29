---
title: "Bucles: expresión while...do (F#)"
description: "Vea cómo el while... hacer expresión se utiliza para realizar la ejecución reiterativa (bucle) mientras una condición de prueba especificada es true."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0416ffca-7ed9-4aff-9493-e001fdba8c9b
ms.openlocfilehash: 6a186d75dcda383764949c2cd3b09bc9e3d1080a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
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
