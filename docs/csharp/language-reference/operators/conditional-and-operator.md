---
title: Operador &amp;&amp; (Referencia de C#)
ms.date: 11/06/2018
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: d0e6d9a5aedc7dc87393e3dea070bf442b3268dc
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "43529240"
---
# <a name="ampamp-operator-c-reference"></a>Operador &amp;&amp; (Referencia de C#)

El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el AND lógico de sus operandos [bool](../keywords/bool.md). El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`. De lo contrario, el resultado es `false`. Si el primer operando se evalúa como `false`, no se evalúa el segundo operando y el resultado de la operación es `false`. En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

El [operador AND lógico](and-operator.md) `&` también calcula el AND lógico de sus operandos `bool`, pero siempre evalúa ambos operandos.

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador AND lógico condicional. Pero si un tipo definido por el usuario sobrecarga los operadores [AND lógico](and-operator.md), [true](../keywords/true-operator.md) y [false](../keywords/false-operator.md) de una manera determinada, la operación `&&` se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores lógicos condicionales](~/_csharplang/spec/expressions.md#conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador ||](conditional-or-operator.md)
- [Operador \!](logical-negation-operator.md)
- [Operador &](and-operator.md)
