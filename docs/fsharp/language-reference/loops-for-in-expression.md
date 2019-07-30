---
title: 'Bucles: expresión for...in'
description: Vea cómo F# ... en, la construcción de bucle de expresión se usa para iterar por las coincidencias de un patrón en una colección Enumerable.
ms.date: 05/16/2016
ms.openlocfilehash: 640b0f91f6c641f3b49a99dc67abe7e4c31911ea
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630717"
---
# <a name="loops-forin-expression"></a>Bucles: expresión for...in

Esta construcción de bucle se usa para iterar por las coincidencias de un patrón en una colección Enumerable como una expresión de intervalo, una secuencia, una lista, una matriz u otra construcción que admita la enumeración.

## <a name="syntax"></a>Sintaxis

```fsharp
for pattern in enumerable-expression do
    body-expression
```

## <a name="remarks"></a>Comentarios

La `for...in` expresión se puede comparar con la `for each` instrucción en otros lenguajes .net porque se usa para recorrer los valores de una colección Enumerable. Sin embargo `for...in` , también admite la coincidencia de patrones en la colección en lugar de simplemente la iteración en toda la colección.

La expresión Enumerable se puede especificar como una colección Enumerable o, mediante `..` el operador, como un intervalo en un tipo entero. Las colecciones enumerables incluyen listas, secuencias, matrices, conjuntos, asignaciones, etc. Se `System.Collections.IEnumerable` puede usar cualquier tipo que implemente.

Al expresar un intervalo mediante el `..` operador, puede usar la sintaxis siguiente.

*iniciar* .. *finish*

También puede usar una versión que incluya un incremento denominado *SKIP*, como en el código siguiente.

*iniciar* .. *omitir* ... *finish*

Cuando se usan intervalos enteros y una variable de contador simple como patrón, el comportamiento típico es incrementar la variable de contador en 1 en cada iteración, pero si el intervalo incluye un valor de omisión, el contador se incrementa en su lugar por el valor de omisión.

Los valores coincidentes en el patrón también se pueden utilizar en la expresión del cuerpo.

En los siguientes ejemplos de código se muestra el `for...in` uso de la expresión.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5201.fs)]

La salida es la siguiente.

```
1
5
100
450
788
```

En el ejemplo siguiente se muestra cómo crear un bucle sobre una secuencia y cómo usar un patrón de tupla en lugar de una variable simple.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5202.fs)]

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

En el ejemplo siguiente se muestra cómo recorrer un intervalo entero simple.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5203.fs)]

La salida de function1 es como se indica a continuación.

```
1 2 3 4 5 6 7 8 9 10
```

En el ejemplo siguiente se muestra cómo recorrer en bucle un intervalo con un salto de 2, que incluye todos los demás elementos del intervalo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5204.fs)]

La salida de `function2` es como se indica a continuación.

```
1 3 5 7 9
```

En el ejemplo siguiente se muestra cómo usar un intervalo de caracteres.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5205.fs)]

La salida de `function3` es como se indica a continuación.

```
a b c d e f g h i j k l m n o p q r s t u v w x y z
```

En el ejemplo siguiente se muestra cómo usar un valor de SKIP negativo para una iteración inversa.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5208.fs)]

La salida de `function4` es como se indica a continuación.

```
10 9 8 7 6 5 4 3 2 1 ... Lift off!
```

El principio y el final del intervalo también pueden ser expresiones, como las funciones, como en el código siguiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5206.fs)]

La salida de `function5` con esta entrada es como se indica a continuación.

```
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

En el ejemplo siguiente se muestra el uso de un carácter\_comodín () cuando el elemento no es necesario en el bucle.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5207.fs)]

La salida es la siguiente.

```
Number of elements in list1: 5
```

`Note`Puede usar `for...in` en expresiones de secuencia y otras expresiones de cálculo, en cuyo caso se utiliza una versión personalizada `for...in` de la expresión. Para obtener más información, vea [secuencias](sequences.md), [flujos de trabajo asincrónicos](asynchronous-workflows.md)y expresiones de [cálculo](computation-expressions.md).

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Bucles `for...to`Expresiones](loops-for-to-expression.md)
- [Bucles `while...do`Expresiones](loops-while-do-expression.md)
