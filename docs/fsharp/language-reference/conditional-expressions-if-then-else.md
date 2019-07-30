---
title: 'Expresiones condicionales: if... después... demás'
description: Obtenga información sobre cómo escribir expresiones condicionales en F# para ejecutar distintas ramas de código.
ms.date: 05/16/2016
ms.openlocfilehash: 825149bf296eded3cc2b4d8847ba4d82bea40cdc
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630397"
---
# <a name="conditional-expressions-ifthenelse"></a>Expresiones condicionales:`if...then...else`

La `if...then...else` expresión ejecuta distintas bifurcaciones de código y también se evalúa como un valor diferente en función de la expresión booleana dada.

## <a name="syntax"></a>Sintaxis

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Comentarios

En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa `true`como; de lo contrario, *expression2* se ejecuta.

A diferencia de otros lenguajes, `if...then...else` la construcción es una expresión, no una instrucción. Esto significa que genera un valor, que es el valor de la última expresión de la bifurcación que se ejecuta. Los tipos de los valores generados en cada bifurcación deben coincidir. Si no hay ninguna rama `else` explícita, su tipo es `unit`. Por lo tanto, si el tipo `then` de la bifurcación es cualquier `unit`tipo que no sea, `else` debe haber una rama con el mismo tipo de valor devuelto. Al encadenar `if...then...else` expresiones juntas, puede usar la palabra `elif` clave en lugar `else if`de; son equivalentes.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo usar la `if...then...else` expresión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
