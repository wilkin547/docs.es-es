---
title: 'Operador /: Referencia de C#'
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286538"
---
# <a name="-operator-c-reference"></a>Operador / (Referencia de C#)

El operador de división `/` divide su primer operando por su segundo operando. Todos los tipos numéricos admiten el operador de división.

## <a name="integer-division"></a>División de enteros

Para los operandos de tipos enteros, el resultado del operador `/` es de un tipo entero y equivale al cociente de los dos operandos redondeados hacia cero:

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

Para obtener el cociente de los dos operandos como número de punto flotante, use el tipo `float`, `double` o `decimal`:

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a>División de punto flotante

Para los tipos `float`, `double` y `decimal`, el resultado del operador `/` es el cociente de los dos operandos:

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

Si uno de los operandos es `decimal`, otro operando no puede ser `float` ni `double`, ya que ni `float` ni `double` se convierte de forma implícita a `decimal`. Debe convertir explícitamente el operando `float` o `double` al tipo `decimal`. Para obtener más información sobre las conversiones implícitas entre tipos numéricos, consulte [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `/`. Cuando se sobrecarga el operador `/`, el [operador de asignación de división](division-assignment-operator.md) `/=` también se sobrecarga de modo implícito.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección sobre [operadores de división](~/_csharplang/spec/expressions.md#division-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Operador %](remainder-operator.md)
