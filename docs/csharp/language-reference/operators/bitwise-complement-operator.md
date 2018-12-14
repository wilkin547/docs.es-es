---
title: Operador ~ (Referencia de C#)
ms.date: 11/05/2018
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 1bcb07c5639a098e3a8c566e92083ca0d48efb81
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153220"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="11592-102">Operador ~ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="11592-102">~ Operator (C# Reference)</span></span>

<span data-ttu-id="11592-103">El operador de complemento bit a bit `~` es un operador unario que genera un complemento bit a bit de su operando mediante la inversión de cada bit.</span><span class="sxs-lookup"><span data-stu-id="11592-103">The bitwise complement operator `~` is a unary operator that produces a bitwise complement of its operand by reversing each bit.</span></span> <span data-ttu-id="11592-104">Todos los tipos de enteros admiten el operador `~`.</span><span class="sxs-lookup"><span data-stu-id="11592-104">All integer types support the `~` operator.</span></span>

> [!NOTE]
> <span data-ttu-id="11592-105">El símbolo `~` también se usa para declarar finalizadores.</span><span class="sxs-lookup"><span data-stu-id="11592-105">The `~` symbol is also used to declare finalizers.</span></span> <span data-ttu-id="11592-106">Para obtener más información, vea [Finalizadores](../../programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="11592-106">For more information, see [Finalizers](../../programming-guide/classes-and-structs/destructors.md).</span></span>

<span data-ttu-id="11592-107">En el siguiente ejemplo se muestra el uso del operador `~`:</span><span class="sxs-lookup"><span data-stu-id="11592-107">The following example demonstrates the usage of the `~` operator:</span></span>

[!code-csharp-interactive[bitwise NOT](~/samples/snippets/csharp/language-reference/operators/BitwiseComplementExamples.cs#Example)]

> [!NOTE]
> <span data-ttu-id="11592-108">En el ejemplo anterior se usan los literales binarios [introducidos en C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) y [mejorados en C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="11592-108">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced  in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="11592-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="11592-109">Operator overloadability</span></span>

<span data-ttu-id="11592-110">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `~`.</span><span class="sxs-lookup"><span data-stu-id="11592-110">User-defined types can [overload](../keywords/operator.md) the `~` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="11592-111">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="11592-111">C# language specification</span></span>

<span data-ttu-id="11592-112">Para más información, vea la sección [Operador de complemento bit a bit](~/_csharplang/spec/expressions.md#bitwise-complement-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="11592-112">For more information, see the [Bitwise complement operator](~/_csharplang/spec/expressions.md#bitwise-complement-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="11592-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="11592-113">See also</span></span>

- [<span data-ttu-id="11592-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="11592-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="11592-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="11592-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="11592-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="11592-116">C# Operators</span></span>](index.md)
- [<span data-ttu-id="11592-117">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="11592-117">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)
- [<span data-ttu-id="11592-118">Operador &</span><span class="sxs-lookup"><span data-stu-id="11592-118">& operator</span></span>](and-operator.md)
- [<span data-ttu-id="11592-119">Operador |</span><span class="sxs-lookup"><span data-stu-id="11592-119">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="11592-120">Operador ^</span><span class="sxs-lookup"><span data-stu-id="11592-120">^ operator</span></span>](xor-operator.md)
