---
title: '>Operador = - Referencia de C#'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 0dd3aa8976c10f0adc5dc7620237991202f772ee
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545551"
---
# <a name="-operator-c-reference"></a>Operador >= (referencia de C#)

El operador relacional "mayor o igual que" `>=` devuelve `true` si su primer operando es mayor o igual que el segundo; en caso contrario, devuelve `false`. Todos los valores numéricos y los tipos de enumeración admiten el operador `>=`. Para los operandos del mismo tipo [enum](../keywords/enum.md), se comparan los valores correspondientes del tipo entero subyacente.

> [!NOTE]
> Para los operadores relacionales `==`, `>`, `<`, `>=` y `<=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`. Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`. Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.

En el siguiente ejemplo se muestra el uso del operador `>=`:

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `>=`. Si un tipo sobrecarga el operador "mayor o igual que" `>=`, también debe sobrecargar el [operador "menor o igual que"](less-than-equal-operator.md) `<=`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador >](greater-than-operator.md)
- [Operador ==](equality-operators.md#equality-operator-)
- <xref:System.IComparable%601?displayProperty=nameWithType>
