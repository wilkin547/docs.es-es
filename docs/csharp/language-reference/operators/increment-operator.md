---
title: Operador ++ - Referencia de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
ms.openlocfilehash: db716f0d8cfe252462abeee9c80baaab880e212b
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235649"
---
# <a name="-operator-c-reference"></a>Operador ++ (Referencia de C#)

El operador de incremento unario `++` incrementa su operando en 1. Se admite en dos formas: el operador de incremento postfijo (`x++`) y el operador de incremento prefijo (`++x`).

## <a name="postfix-increment-operator"></a>Operador de incremento de postfijo

El resultado de `x++` es el valor de `x` *antes* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[postfix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PostfixIncrement)]

## <a name="prefix-increment-operator"></a>Operador de incremento prefijo

El resultado de `++x` es el valor de `x` *después* de la operación, tal y como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[prefix increment](~/samples/snippets/csharp/language-reference/operators/DecrementAndIncrementExamples.cs#PrefixIncrement)]

## <a name="remarks"></a>Comentarios

El operador de incremento está predefinido para todos los [tipos enteros](../keywords/integral-types-table.md) (incluido el tipo [char](../keywords/char.md)), los [tipos de punto flotante](../keywords/floating-point-types-table.md) y cualquier tipo [enum](../keywords/enum.md).

Un operando del operador de incremento debe ser una variable, un acceso de [propiedad](../../programming-guide/classes-and-structs/properties.md) o un acceso de [indizador](../../../csharp/programming-guide/indexers/index.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `++`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea las secciones [Operadores postfijos de incremento y decremento](~/_csharplang/spec/expressions.md#postfix-increment-and-decrement-operators) y [Prefijo de incremento y decremento de operadores](~/_csharplang/spec/expressions.md#prefix-increment-and-decrement-operators) de la [Especificación del lenguaje C# ](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador --](decrement-operator.md)
- [Cómo: Aumentar y disminuir punteros](../../programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
