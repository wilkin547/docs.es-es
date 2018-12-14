---
title: 'Operador ?: (Referencia de C#)'
ms.date: 11/20/2018
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: cc9bde1d60a3272e2f24cfc05761171a31029c75
ms.sourcegitcommit: 6ae7cdd0437a32884556dd4826ca90e957b7a4e3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2018
ms.locfileid: "50980627"
---
# <a name="-operator-c-reference"></a>Operador ?: (Referencia de C#)

El operador condicional `?:`, normalmente conocido como operador condicional ternario, evalúa una expresión booleana y devuelve el resultado de evaluar una de dos expresiones, en función de que la expresión booleana se evalúe como `true` o `false`. A partir C# 7.2, la [expresión condicional ref](#conditional-ref-expression) devuelve la referencia al resultado de una de las dos expresiones.

La sintaxis del operador condicional es la siguiente:

```csharp
condition ? consequence : alternative
```

La expresión `condition` debe evaluarse como `true` o `false`. Si `condition` se evalúa como `true`, se evalúa la expresión `consequence` y su resultado se convierte en el resultado de la operación. Si `condition` se evalúa como `false`, se evalúa la expresión `alternative` y su resultado se convierte en el resultado de la operación. Solo se evalúan `consequence` o `alternative`.

Los tipos de `consequence` y `alternative` deben coincidir o debe haber una conversión implícita de un tipo al otro.

El operador condicional es asociativo a la derecha, es decir, una expresión de la forma

```csharp
a ? b : c ? d : e
```

se evalúa como

```csharp
a ? b : (c ? d : e)
```

En el siguiente ejemplo se muestra el uso del operador condicional:

[!code-csharp[non ref condtional](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalValue)]

## <a name="conditional-ref-expression"></a>Expresión condicional ref

A partir C# 7.2, puede utilizar la expresión condicional ref para devolver la referencia al resultado de una de las dos expresiones. Puede asignar esa referencia a una variable [ref local](../keywords/ref.md#ref-locals) o [ref readonly local](../keywords/ref.md#ref-readonly-locals), o bien usarla como un [valor devuelto de referencia](../keywords/ref.md#reference-return-values) o como un [parámetro de método `ref`](../keywords/ref.md#passing-an-argument-by-reference).

La sintaxis de la expresión condicional ref es la siguiente:

```csharp
condition ? ref consequence : ref alternative
```

Al igual que el operador condicional original, la expresión condicional ref evalúa solo una de las dos expresiones: ya sea `consequence` o `alternative`.

En el caso de la expresión condicional ref, los tipos de `consequence` y `alternative` deben coincidir.

En el siguiente ejemplo se muestra el uso de la expresión condicional ref:

[!code-csharp[conditional ref](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#ConditionalRef)]

Para más información, vea la [nota de propuesta de características](https://github.com/dotnet/csharplang/blob/master/proposals/csharp-7.2/conditional-ref.md).

## <a name="conditional-operator-and-an-ifelse-statement"></a>Operador condicional y una instrucción `if..else`

El uso del operador condicional a través de una instrucción [if-else](../keywords/if-else.md) podría traducirse en código más conciso en aquellos casos en los que potencialmente tenga que calcular un valor. El ejemplo siguiente muestra dos maneras de clasificar un entero como negativo o no negativo:

[!code-csharp[conditional and if-else](~/samples/snippets/csharp/language-reference/operators/ConditionalExamples.cs#CompareWithIf)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

El operador condicional no se puede sobrecargar.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre [operadores condicionales](~/_csharplang/spec/expressions.md#conditional-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Instrucción if-else](../keywords/if-else.md)
- [Operadores ?. y ?[]](null-conditional-operators.md)
- [Operador !](null-coalescing-operator.md)
- [ref (palabra clave)](../keywords/ref.md)
