---
title: 'Operadores de comparación: referencia de C#'
description: Obtenga información sobre los operadores de comparación de C# que puede usar para comprobar el orden de los valores numéricos.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: ea8d8ab5ac14ec94c647ed33cca6f949a90737bd
ms.sourcegitcommit: dd3b897feb5c4ac39732bb165848e37a344b0765
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2019
ms.locfileid: "64431614"
---
# <a name="comparison-operators-c-reference"></a>Operadores de comparación (referencia de C#)

Los operadores de la comparación [`<` (menor que)](#less-than-operator-), [`>` (mayor que)](#greater-than-operator-), [`<=` (menor o igual que)](#less-than-or-equal-operator-) y [`>=` (mayor o igual que)](#greater-than-or-equal-operator-), también conocidos como relacionales, comparan sus operandos. Estos operadores admiten todos los tipos numéricos [integrales](../keywords/integral-types-table.md) y de [punto flotante](../keywords/floating-point-types-table.md).

> [!NOTE]
> Para los operadores `==`, `<`, `>`, `<=` y `>=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Los tipos de enumeración también admiten operadores de comparación. Para los operandos del mismo tipo [enum](../keywords/enum.md), se comparan los valores correspondientes del tipo entero subyacente.

Los [operadores `==` y `!=`](equality-operators.md) comprueban si los operandos son iguales.

## <a name="less-than-operator-"></a>Operador menor que \<

El operador `<` devuelve `true` si su primer operando es menor que el segundo; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a>Operador mayor que >

El operador `>` devuelve `true` si su primer operando es mayor que el segundo; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Operador menor o igual que \<=

El operador `<=` devuelve `true` si su primer operando es menor o igual que el segundo; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Operador mayor o igual que >=

El operador `>=` devuelve `true` si su primer operando es mayor o igual que el segundo; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `<`, `>`, `<=` y `>=`.

Si un tipo sobrecarga uno de los operadores `<` o `>`, también debe sobrecargar `<` y `>`. Si un tipo sobrecarga uno de los operadores `<=` o `>=`, también debe sobrecargar `<=` y `>=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Operadores de igualdad](equality-operators.md)
