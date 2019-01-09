---
title: 'Operador ==: Referencia de C#'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655964"
---
# <a name="-operator-c-reference"></a>Operador == (Referencia de C#)

El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.

## <a name="value-types-equality"></a>Igualdad entre tipos de valor

Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> Para los operadores relacionales `==`, `>`, `<`, `>=` y `<=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.

De forma predeterminada, el operador `==` no está definido por un tipo de [estructura](../keywords/struct.md) definido por el usuario. Un tipo definido por el usuario puede [sobrecargar](#operator-overloadability) el operador `==`.

A partir de C# 7,3, los operadores `==` y [`!=`](not-equal-operator.md) son compatibles con las [tuplas](../../tuples.md) de C#. Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).

## <a name="string-equality"></a>Igualdad entre cadenas

Dos operandos [string](../keywords/string.md) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

Es la comparación de ordinales que distingue entre mayúsculas de minúsculas. Para obtener más información sobre cómo comparar cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).

## <a name="reference-types-equality"></a>Igualdad entre tipos de referencia

Dos operandos de tipos de referencia (excepto `string`) son iguales si hacen referencia al mismo objeto:

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

En el ejemplo se muestra que el operador `==` es compatible con los tipos de referencia definidos por el usuario. Sin embargo, un tipo de referencia definido por el usuario puede sobrecargar el operador `==`. Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `==`. Si un tipo sobrecarga el operador de igualdad `==`, también debe sobrecargar el [operador de desigualdad](not-equal-operator.md) `!=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Comparaciones de igualdad](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
