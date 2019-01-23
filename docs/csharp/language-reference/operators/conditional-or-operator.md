---
title: 'Operador||: Referencia de C#'
ms.custom: seodec18
ms.date: 11/06/2018
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 079c021eb68ece097c7f644416f1e9469a82dcea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415434"
---
# <a name="-operator-c-reference"></a>Operador || (Referencia de C#)

El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el OR lógico de sus operandos [bool](../keywords/bool.md). El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`. De lo contrario, el resultado es `false`. Si el primer operando se evalúa como `true`, no se evalúa el segundo operando y el resultado de la operación es `true`. En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

El [operador OR lógico](or-operator.md) `|` también calcula el OR lógico de sus operandos `bool`, pero siempre evalúa ambos.

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Un tipo definido por el usuario no puede sobrecargar el operador OR lógico condicional. Pero si un tipo definido por el usuario sobrecarga los operadores [OR lógico](or-operator.md) y [true y false](../keywords/true-false-operators.md) de una manera determinada, la operación `||` se puede evaluar para los operandos de ese tipo. Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea la sección [Operadores lógicos condicionales](~/_csharplang/spec/expressions.md#conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador &&](conditional-and-operator.md)
- [\! operator](logical-negation-operator.md)
- [Operador |](or-operator.md)
