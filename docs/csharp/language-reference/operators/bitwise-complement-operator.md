---
title: Operador ~ - Referencia de C#
ms.custom: seodec18
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 57e5baee423c0b5d9292d0ad4cbf909646eb3a38
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235730"
---
# <a name="-operator-c-reference"></a>Operador ~ (Referencia de C#)

El operador de complemento bit a bit `~` es un operador unario que genera un complemento bit a bit de su operando mediante la inversión de cada bit. Todos los tipos de enteros admiten el operador `~`.

> [!NOTE]
> El símbolo `~` también se usa para declarar finalizadores. Para obtener más información, vea [Finalizadores](../../programming-guide/classes-and-structs/destructors.md).

En el siguiente ejemplo se muestra el uso del operador `~`:

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> En el ejemplo anterior se usan los literales binarios [introducidos en C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) y [mejorados en C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

## <a name="operator-overloadability"></a>Posibilidad de sobrecarga del operador

Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `~`.

## <a name="c-language-specification"></a>Especificación del lenguaje C#

Para más información, vea la sección [Operador de complemento bit a bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).

## <a name="see-also"></a>Vea también

- [Referencia de C#](../index.md)
- [Guía de programación de C#](../../programming-guide/index.md)
- [Operadores de C#](index.md)
- [Finalizadores](../../programming-guide/classes-and-structs/destructors.md)
- [Operador &](and-operator.md)
- [Operador |](or-operator.md)
- [Operador ^](xor-operator.md)
