---
title: 'Operadores de igualdad: referencia de C#'
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 297285ccb9aba7eae1d70a7d28a62241646a023c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334164"
---
# <a name="equality-operators-c-reference"></a>Operadores de igualdad (referencia de C#)

Los operadores [`==` (igualdad)](#equality-operator-) y [`!=` (desigualdad)](#inequality-operator-) comprueban si los operandos son iguales.

## <a name="equality-operator-"></a>Operador de igualdad ==

El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.

### <a name="value-types-equality"></a>Igualdad entre tipos de valor

Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Para los operadores de igualdad y relacionales `==`, `>`, `<`, `>=` y `<=`, si uno de los operandos no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado de la operación será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.

Los tipos [struct](../keywords/struct.md) definidos por el usuario no son compatibles con el operador `==` de forma predeterminada. Para admitir el operador `==`, un elemento struct definido por el usuario debe [sobrecargarlo](#operator-overloadability).

A partir de C# 7.3, los operadores `==` y `!=` son compatibles con las [tuplas](../../tuples.md) de C#. Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).

### <a name="string-equality"></a>Igualdad entre cadenas

Dos operandos [string](../keywords/string.md) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Es la comparación de ordinales que distingue entre mayúsculas de minúsculas. Para obtener más información sobre la comparación de cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).

### <a name="reference-types-equality"></a>Igualdad entre tipos de referencia

Dos operandos de tipos de referencia (excepto `string`) son iguales si hacen referencia al mismo objeto:

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

Como se muestra en el ejemplo, el operador `==` es compatible de forma predeterminada con los tipos de referencia definidos por el usuario. Sin embargo, un tipo de referencia definido por el usuario puede sobrecargar el operador `==`. Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.

## <a name="inequality-operator-"></a>Operador de desigualdad !=

El operador de desigualdad (`!=`) devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`. Para los operandos de los [tipos integrados](../keywords/built-in-types-table.md), la expresión `x != y` genera el mismo resultado que la expresión `!(x == y)`. Para obtener más información sobre la igualdad de tipos, vea la sección [Operador de igualdad](#equality-operator-).

En el siguiente ejemplo se muestra el uso del operador `!=`:

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `==` y `!=`. Si un tipo sobrecarga uno de los dos operadores, también debe sobrecargar el otro.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [Comparaciones de igualdad](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
