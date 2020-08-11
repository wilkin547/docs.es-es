---
title: Operadores de comparación (referencia de C#)
description: Obtenga información sobre los operadores de comparación de C# que puede usar para comprobar el orden de los valores numéricos.
ms.date: 05/11/2020
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
ms.openlocfilehash: 9fa739d8b5461d4043f3ae51f5d14949a95c68e5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916883"
---
# <a name="comparison-operators-c-reference"></a>Operadores de comparación (referencia de C#)

Los operadores de la comparación [`<` (menor que)](#less-than-operator-), [`>` (mayor que)](#greater-than-operator-), [`<=` (menor o igual que)](#less-than-or-equal-operator-) y [`>=` (mayor o igual que)](#greater-than-or-equal-operator-), también conocidos como relacionales, comparan sus operandos. Estos operadores se admiten en todos los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md).

> [!NOTE]
> Para los operadores `==`, `<`, `>`, `<=` y `>=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

El tipo [char](../builtin-types/char.md) también admite operadores de comparación. En el caso de los operandos `char`, se comparan los códigos de caracteres correspondientes.

Los tipos de enumeración también admiten operadores de comparación. Para los operandos del mismo tipo [enum](../builtin-types/enum.md), se comparan los valores correspondientes del tipo entero subyacente.

Los [operadores `==` y `!=`](equality-operators.md) comprueban si los operandos son iguales.

## <a name="less-than-operator-"></a>Operador menor que \<

El operador `<` devuelve `true` si el operando izquierdo es menor que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than example](snippets/shared/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>Operador mayor que >

El operador `>` devuelve `true` si el operando izquierdo es mayor que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than example](snippets/shared/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>Operador menor o igual que \<=

El operador `<=` devuelve `true` si el operando izquierdo es menor o igual que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[less than or equal example](snippets/shared/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>Operador mayor o igual que >=

El operador `>=` devuelve `true` si el operando izquierdo es mayor o igual que el derecho; en caso contrario, devuelve `false`.

[!code-csharp-interactive[greater than or equal example](snippets/shared/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `<`, `>`, `<=` y `>=`.

Si un tipo sobrecarga uno de los operadores `<` o `>`, también debe sobrecargar `<` y `>`. Si un tipo sobrecarga uno de los operadores `<=` o `>=`, también debe sobrecargar `<=` y `>=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Operadores y expresiones de C#](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Operadores de igualdad](equality-operators.md)
