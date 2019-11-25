---
title: 'Bucles: expresión for...to'
description: Vea cómo F# ... la expresión to se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283900"
---
# <a name="loops-forto-expression"></a>Bucles: expresión for...to

La expresión `for...to` se usa para iterar en un bucle en un intervalo de valores de una variable de bucle.

## <a name="syntax"></a>Sintaxis

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Comentarios

El tipo del identificador se deduce del tipo de las expresiones de *Inicio* y *finalización* . Los tipos de estas expresiones deben ser enteros de 32 bits.

A pesar de ser técnicamente una expresión, `for...to` es más similar a una instrucción tradicional en un lenguaje de programación imperativo. El tipo de valor devuelto para la *expresión Body* debe ser `unit`. En los ejemplos siguientes se muestran varios usos de la expresión `for...to`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

La salida del código anterior es la siguiente.

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Bucles: expresión `for...in`](loops-for-in-expression.md)
- [Bucles: expresión `while...do`](loops-while-do-expression.md)
