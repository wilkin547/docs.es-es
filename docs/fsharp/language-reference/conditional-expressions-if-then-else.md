---
title: 'Expresiones condicionales: if... then...else (F#)'
description: 'Obtenga información acerca de cómo escribir expresiones condicionales en F # para ejecutar distintas bifurcaciones de código.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: bfb985f09be91034894e1d3eba88cebef6bb3fd4
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="conditional-expressions-ifthenelse"></a>Expresiones condicionales: `if...then...else`

El `if...then...else` expresión ejecuta diferentes bifurcaciones de código y también se evalúa como un valor diferente dependiendo de la expresión booleana especificada.


## <a name="syntax"></a>Sintaxis

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a>Comentarios
En la sintaxis anterior, *expression1* se ejecuta cuando la expresión booleana se evalúa como `true`; en caso contrario, *expression2* se ejecuta.

A diferencia de otros lenguajes, la `if...then...else` construcción es una expresión, no una instrucción. Esto significa que genera un valor, que es el valor de la última expresión de la bifurcación que se ejecuta. Los tipos de los valores generados en cada bifurcación deben coincidir. Si no hay ningún `else` rama, su tipo es `unit`. Por lo tanto, si el tipo de la `then` bifurcación es cualquier tipo distinto de `unit`, debe haber un `else` rama con el mismo tipo de valor devuelto. Cuando se encadenan `if...then...else` expresiones, puede usar la palabra clave `elif` en lugar de `else if`; son equivalentes.

## <a name="example"></a>Ejemplo
En el ejemplo siguiente se muestra cómo utilizar el `if...then...else` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

