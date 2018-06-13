---
title: 'Bucles: expresión for...in (F#)'
description: 'Vea cómo la estructura de F # for.. en expresión la construcción de bucle se utiliza para recorrer en iteración las coincidencias de un patrón en una colección enumerable.'
ms.date: 05/16/2016
ms.openlocfilehash: 926f0a9940021b3dc0deefc12ea158c35975e949
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564079"
---
# <a name="loops-forin-expression"></a>Bucles: expresión for...in

Esta construcción de bucle se utiliza para recorrer en iteración las coincidencias de un patrón en una colección enumerable como una expresión de intervalo, secuencia, lista, matriz u otra construcción que admita la enumeración.


## <a name="syntax"></a>Sintaxis

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Comentarios
El `for...in` expresión se puede comparar con la `for each` instrucción en otros lenguajes .NET porque se usa para iterar por los valores de una colección enumerable. Sin embargo, `for...in` también admite el patrón de coincidencia en la colección en lugar de solo la iteración a través de toda la colección.

La expresión enumerable puede especificarse como una colección enumerable o, mediante el `..` operador, como un intervalo en un tipo entero. Las colecciones enumerables incluyen listas, secuencias, matrices, conjuntos, asignaciones y así sucesivamente. Cualquier tipo que implemente `System.Collections.IEnumerable` puede utilizarse.

Al expresar un intervalo mediante el `..` operador, puede utilizar la siguiente sintaxis.

*iniciar* ... *Finalizar*

También puede usar una versión que incluye un incremento denominado el *omitir*, como en el código siguiente.

*iniciar* ... *omitir* ... *Finalizar*

Cuando utiliza intervalos de enteros y una variable de contador simple como un patrón, el comportamiento típico es incrementar la variable de contador en 1 en cada iteración, pero si el intervalo incluye un valor de salto, el contador se incrementa en el valor de omisión en su lugar.

Los valores coincidentes en el modelo también pueden utilizarse en la expresión del cuerpo.

Ejemplos de código siguientes muestran el uso de la `for...in` expresión.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

La salida es la siguiente.

```
1
5
100
450
788
```

En el ejemplo siguiente se muestra cómo crear bucles a través de una secuencia y cómo utilizar un tupla (modelo) en lugar de una variable simple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

La salida es la siguiente.

```
1 squared is 1
2 squared is 4
3 squared is 9
4 squared is 16
5 squared is 25
6 squared is 36
7 squared is 49
8 squared is 64
9 squared is 81
10 squared is 100
```

En el ejemplo siguiente se muestra cómo recorrer en iteración un intervalo de enteros simple.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

La salida de function1 es como sigue.

```
1 2 3 4 5 6 7 8 9 10
```

En el ejemplo siguiente se muestra cómo recorrer en iteración un intervalo con un salto de 2, que incluye todos los elementos del intervalo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

La salida de `function2` es como sigue.

```
1 3 5 7 9
```

En el ejemplo siguiente se muestra cómo usar un intervalo de caracteres.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

La salida de `function3` es como sigue.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

En el ejemplo siguiente se muestra cómo usar un valor negativo skip para una iteración inversa.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

La salida de `function4` es como sigue.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

El principio y el final del intervalo también pueden ser expresiones, como funciones, como en el código siguiente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

La salida de `function5` con esta entrada es como sigue.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

En el ejemplo siguiente se muestra el uso de un carácter comodín (_) cuando el elemento no es necesaria en el bucle.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

La salida es la siguiente.

```
Number of elements in list1: 5
```

`Note` Puede usar `for...in` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso una versión personalizada de la `for...in` se utiliza la expresión. Para obtener más información, consulte [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md), y [expresiones de cálculo](computation-expressions.md).


## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

[Bucles: expresión `for...to`](loops-for-to-expression.md)

[Bucles: expresión `while...do`](loops-while-do-expression.md)
