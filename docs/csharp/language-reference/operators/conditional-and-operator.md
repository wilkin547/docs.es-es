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
# <a name="ampamp-operator-c-reference"></a><span data-ttu-id="492c2-102">Operador &amp;&amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="492c2-102">&amp;&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="492c2-103">El operador AND lógico condicional `&&`, también denominado operador AND lógico "de cortocircuito", calcula el AND lógico de sus operandos [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="492c2-103">The conditional logical AND operator `&&`, also known as the "short-circuiting" logical AND operator, computes the logical AND of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="492c2-104">El resultado de `x && y` es `true` si `x` y `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="492c2-104">The result of `x && y` is `true` if both `x` and `y` evaluate to `true`.</span></span> <span data-ttu-id="492c2-105">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="492c2-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="492c2-106">Si el primer operando se evalúa como `false`, no se evalúa el segundo operando y el resultado de la operación es `false`.</span><span class="sxs-lookup"><span data-stu-id="492c2-106">If the first operand evaluates to `false`, the second operand is not evaluated and the result of operation is `false`.</span></span> <span data-ttu-id="492c2-107">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="492c2-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical AND](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#And)]

<span data-ttu-id="492c2-108">El [operador AND lógico](and-operator.md) `&` también calcula el AND lógico de sus operandos `bool`, pero siempre evalúa ambos operandos.</span><span class="sxs-lookup"><span data-stu-id="492c2-108">The [logical AND operator](and-operator.md) `&` also computes the logical AND of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="492c2-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="492c2-109">Operator overloadability</span></span>

<span data-ttu-id="492c2-110">Un tipo definido por el usuario no puede sobrecargar el operador AND lógico condicional.</span><span class="sxs-lookup"><span data-stu-id="492c2-110">A user-defined type cannot overload the conditional logical AND operator.</span></span> <span data-ttu-id="492c2-111">Pero si un tipo definido por el usuario sobrecarga los operadores [AND lógico](and-operator.md), [true](../keywords/true-operator.md) y [false](../keywords/false-operator.md) de una manera determinada, la operación `&&` se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="492c2-111">However, if a user-defined type overloads the [logical AND](and-operator.md), [true](../keywords/true-operator.md), and [false](../keywords/false-operator.md) operators in a certain way, the `&&` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="492c2-112">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="492c2-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="492c2-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="492c2-113">C# language specification</span></span>

<span data-ttu-id="492c2-114">Para obtener más información, vea la sección [Operadores lógicos condicionales](~/_csharplang/spec/expressions.md#conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="492c2-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="492c2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="492c2-115">See also</span></span>

- [<span data-ttu-id="492c2-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="492c2-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="492c2-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="492c2-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="492c2-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="492c2-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="492c2-119">Operador ||</span><span class="sxs-lookup"><span data-stu-id="492c2-119">|| operator</span></span>](conditional-or-operator.md)
- [<span data-ttu-id="492c2-120">Operador \!</span><span class="sxs-lookup"><span data-stu-id="492c2-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="492c2-121">Operador &</span><span class="sxs-lookup"><span data-stu-id="492c2-121">& operator</span></span>](and-operator.md)
