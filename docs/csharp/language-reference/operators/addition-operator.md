---
title: + Operador (Referencia de C#)
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: ae2774d96bc50afa271fffdea445e640e68c3647
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192309"
---
# <a name="-operator-c-reference"></a>Operador + (Referencia de C#)

El operador `+` se admite de dos formas: un operador más unario o un operador de suma binario.

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) los operadores unarios y binarios `+`. Cuando se sobrecarga un operador `+` binario, el [operador de asignación de suma](addition-assignment-operator.md) `+=` también se sobrecarga de modo implícito.

## <a name="unary-plus-operator"></a>Operador unario más

El operador `+` unario devuelve el valor de su operando. Es compatible con todos los tipos numéricos.

## <a name="numeric-addition"></a>Suma de números

Para tipos numéricos, el operador `+` calcula la suma de sus operandos:

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a>Concatenación de cadenas

Cuando uno o ambos operandos son de tipo [cadena](../keywords/string.md), el operador `+` concatena las representaciones de cadena de sus operandos:

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

A partir de C# 6, la [interpolación de cadenas](../tokens/interpolated.md) proporciona una manera más conveniente de dar formato a las cadenas:

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a>Combinación de delegados

Para los tipos de [delegado](../keywords/delegate.md), el operador `+` devuelve una nueva instancia de delegado que, cuando se invoca, invoca el primer operando y luego invoca el segundo operando. Si alguno de los operandos es `null`, el operador `+` devuelve el valor del otro operando (que también podría ser `null`). El ejemplo siguiente muestra cómo los delegados se pueden combinar con el operador `+`:

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator) y [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator) de la [especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Interpolación de cadenas](../tokens/interpolated.md)
- [Cómo: Concatenar varias cadenas](../../how-to/concatenate-multiple-strings.md)
- [Delegados](../../programming-guide/delegates/index.md)
- [Checked y unchecked](../keywords/checked-and-unchecked.md)
