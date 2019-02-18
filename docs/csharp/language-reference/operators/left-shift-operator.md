---
title: 'Operador <<: Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219442"
---
# <a name="-operator-c-reference"></a>Operador \<\< (Referencia de C#)

El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits definido por su segundo operando. Todos los tipos de enteros admiten el operador `<<`. No obstante, el tipo del segundo operando debe ser [int](../keywords/int.md) o un tipo que tiene una [conversión numérica implícita predefinida](../keywords/implicit-numeric-conversions-table.md) en `int`.

Se descartan los bits de orden superior que están fuera del intervalo del tipo del resultado, y las posiciones de bits vacías de orden inferior se establecen en cero, como se muestra en el ejemplo siguiente:

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a>Recuento de desplazamiento

Para la expresión `x << count`, el recuento de desplazamiento real depende del tipo de `x` como sigue:

- Si el tipo de `x` es [int](../keywords/int.md) o [uint](../keywords/uint.md), el valor de desplazamiento viene dado por los *cinco* bits de orden inferior del segundo operando. Es decir, el valor de desplazamiento se calcula a partir de `count & 0x1F` (o `count & 0b_1_1111`).

- Si el tipo de `x` es [long](../keywords/long.md) o [ulong](../keywords/ulong.md), el valor de desplazamiento viene dado por los *seis* bits de orden inferior del segundo operando. Es decir, el valor de desplazamiento se calcula a partir de `count & 0x3F` (o `count & 0b_11_1111`).

En el ejemplo siguiente se muestra ese comportamiento:

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a>Comentarios

Las operaciones de desplazamiento nunca producen desbordamientos y generan los mismos resultados en contextos [checked y unchecked](../keywords/checked-and-unchecked.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `<<`. Si un tipo definido por el usuario `T` sobrecarga el operador `<<`, el tipo del primer operando debe ser `T` y el tipo del segundo operando debe ser `int`. Cuando se sobrecarga el operador `<<`, el [operador de asignación de desplazamiento a la izquierda](left-shift-assignment-operator.md) `<<=` también se sobrecarga de modo implícito.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre [operadores de desplazamiento](~/_csharplang/spec/expressions.md#shift-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador >>](right-shift-operator.md)
