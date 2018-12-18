---
title: 'Operador &amp;: Referencia de C#'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: a799c0e37d6607e8ff72ab984ff5e540a4e11063
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236380"
---
# <a name="amp-operator-c-reference"></a>Operador &amp; (Referencia de C#)

El operador `&` se admite de dos formas: un operador address-of unario o un operador lógico binario.

## <a name="unary-address-of-operator"></a>Operador address-of unario

El operador `&` unario devuelve la dirección de su operando. Para obtener más información, vea [Cómo: Obtener la dirección de una variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).

El operador address-of `&` requiere un contexto [no seguro](../keywords/unsafe.md).

## <a name="integer-logical-bitwise-and-operator"></a>Operador AND bit a bit lógico entero

Para los tipos enteros, el operador `&` calcula el AND bit a bit lógico de sus operandos:

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> En el ejemplo anterior se usan los literales binarios [introducidos en C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) y [mejorados en C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

Como las operaciones en tipos enteros generalmente se permiten en los tipos de enumeración, el operador `&` también es compatible con los operandos [enum](../keywords/enum.md).

## <a name="boolean-logical-and-operator"></a>Operador AND lógico booleano

Para los operandos [bool](../keywords/bool.md), el operador `&` calcula el AND lógico de sus operandos. El resultado de `x & y` es `true` si tanto `x` como `y` son `true`. De lo contrario, el resultado es `false`.

El operador `&` evalúa ambos, incluso aunque el primero se evalúe como `false`, de modo que el resultado debe ser `false` con independencia del valor del segundo operando. En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

El [operador AND condicional](conditional-and-operator.md) `&&` también calcula el AND lógico de sus operandos, pero evalúa el segundo operando solo si el primero se evalúa como `true`.

Para los operandos de tipo bool que aceptan valores NULL, el comportamiento del operador `&` es coherente con la lógica de tres valores de SQL. Para obtener más información, vea la sección [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `&` binario. Cuando se sobrecarga un operador `&` binario, el [operador de asignación AND](and-assignment-operator.md) `&=` también se sobrecarga de modo implícito.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para obtener más información, vea las secciones [El operador address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) y [Operadores lógicos](~/_csharplang/spec/expressions.md#logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Tipos de puntero](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Operador |](or-operator.md)
- [Operador ^](xor-operator.md)
- [Operador ~](bitwise-complement-operator.md)
- [Operador &&](conditional-and-operator.md)
