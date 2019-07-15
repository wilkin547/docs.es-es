---
title: Operadores de comparación (referencia de C#)
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
ms.openlocfilehash: d3e9bf1356218f223f959b423dfc048972b075d3
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661516"
---
# <a name="comparison-operators-c-reference"></a>Operadores de comparación (referencia de C#)

Los operadores de la comparación [`<` (menor que)](#less-than-operator-), [`>` (mayor que)](#greater-than-operator-), [`<=` (menor o igual que)](#less-than-or-equal-operator-) y [`>=` (mayor o igual que)](#greater-than-or-equal-operator-), también conocidos como relacionales, comparan sus operandos. Estos operadores admiten todos los tipos numéricos [integrales](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md).

> [!NOTE]
> Para los operadores `==`, `<`, `>`, `<=` y `>=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

Los tipos de enumeración también admiten operadores de comparación. Para los operandos del mismo tipo [enum](../keywords/enum.md), se comparan los valores correspondientes del tipo entero subyacente.

Los [operadores `==` y `!=`](equality-operators.md) comprueban si los operandos son iguales.

## <a name="less-than-operator-"></a>Operador menor que \<

El operador `<` devuelve `true` si el operando izquierdo es menor que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>Operador mayor que >

El operador `>` devuelve `true` si el operando izquierdo es mayor que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Operador menor o igual que \<=

El operador `<=` devuelve `true` si el operando izquierdo es menor o igual que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Operador mayor o igual que >=

El operador `>=` devuelve `true` si el operando izquierdo es mayor o igual que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `<`, `>`, `<=` y `>=`.

Si un tipo sobrecarga uno de los operadores `<` o `>`, también debe sobrecargar `<` y `>`. Si un tipo sobrecarga uno de los operadores `<=` o `>=`, también debe sobrecargar `<=` y `>=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores de C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Operadores de igualdad](equality-operators.md)
