---
title: 'Expresiones condicionales: if... then...else (F#)'
description: 'Obtenga información acerca de cómo escribir expresiones condicionales en F # para ejecutar distintas bifurcaciones de código.'
ms.date: 05/16/2016
ms.openlocfilehash: a3ca3c20a659ccf5dc432d0a747ff176ec889e9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563138"
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

