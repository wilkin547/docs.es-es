---
title: Operador -- (Referencia de C#)
ms.date: 11/26/2018
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 0858321d6fe192a55bc548f169c558542238a981
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153345"
---
# <a name="---operator-c-reference"></a>Operador -- (Referencia de C#)

El operador de decremento unario `--` disminuye su operando en 1. Se admite en dos formas: el operador de decremento de postfijo ( `x--`) y el operador de decremento de prefijo (`--x`).

## <a name="postfix-decrement-operator"></a>Operador de decremento de postfijo

El resultado de `x--` es el valor de `x` *antes* de la operación, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[postfix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixDecrement)]

## <a name="prefix-decrement-operator"></a>Operador de decremento de prefijo

El resultado de `--x` es el valor de `x` *después* de la operación, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[prefix decrement](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixDecrement)]

## <a name="remarks"></a>Comentarios

El operador de decremento está predefinido para todos los [tipos enteros](../keywords/integral-types-table.md) (incluido el tipo [char](../keywords/char.md)), los [tipos de punto flotante](../keywords/floating-point-types-table.md) y cualquier tipo [enum](../keywords/enum.md).

Un operando del operador de decremento debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un de [indizador](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `--`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, consulte las secciones [Operadores postfijos de incremento y decremento](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) y [Prefijo de incremento y decremento de operadores](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) de la [Especificación del lenguaje C# ](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador ++](increment-operator.md)
- [Aumento y disminución de punteros](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
