---
title: 'Bucles: expresión while...do'
description: Vea cómo... la expresión do se usa para realizar la ejecución iterativa (bucle) mientras se cumple una condición de prueba especificada.
ms.date: 05/16/2016
ms.openlocfilehash: f05bdd9f8f4b9446d59f68e1231fb75e18e9b526
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630760"
---
# <a name="loops-whiledo-expression"></a>Bucles: expresión while...do

La `while...do` expresión se usa para realizar la ejecución iterativa (en bucle) mientras se cumple una condición de prueba especificada.

## <a name="syntax"></a>Sintaxis

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a>Comentarios

Se evalúa *Test-Expression* ; Si es `true`así, se ejecuta la *expresión Body* y se vuelve a evaluar la expresión de prueba. El *cuerpo-expresión* debe tener el `unit`tipo. Si la expresión de prueba `false`es, finaliza la iteración.

En el ejemplo siguiente se muestra el uso de `while...do` la expresión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

La salida del código anterior es un flujo de números aleatorios entre 1 y 20, el último de los cuales es 10.

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> Puede usar `while...do` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `while...do` de la expresión. Para obtener más información, vea [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y expresiones de [cálculo](computation-expressions.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Bucles `for...in`Expresiones](loops-for-in-expression.md)
- [Bucles `for...to`Expresiones](loops-for-to-expression.md)
