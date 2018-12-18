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
ms.openlocfilehash: f4bb7ada12fbcebcb90fb7cd22d6e6bccad5fb57
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244575"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2b367-102">Operador || (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2b367-102">|| Operator (C# Reference)</span></span>

<span data-ttu-id="2b367-103">El operador OR lógico condicional `||`, también denominado operador OR lógico "de cortocircuito", calcula el OR lógico de sus operandos [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="2b367-103">The conditional logical OR operator `||`, also known as the "short-circuiting" logical OR operator, computes the logical OR of its [bool](../keywords/bool.md) operands.</span></span> <span data-ttu-id="2b367-104">El resultado de `x || y` es `true` si `x` o `y` se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="2b367-104">The result of `x || y` is `true` if either `x` or `y` evaluates to `true`.</span></span> <span data-ttu-id="2b367-105">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="2b367-105">Otherwise, the result is `false`.</span></span> <span data-ttu-id="2b367-106">Si el primer operando se evalúa como `true`, no se evalúa el segundo operando y el resultado de la operación es `true`.</span><span class="sxs-lookup"><span data-stu-id="2b367-106">If the first operand evaluates to `true`, the second operand is not evaluated and the result of operation is `true`.</span></span> <span data-ttu-id="2b367-107">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="2b367-107">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[conditional logical OR](~/samples/snippets/csharp/language-reference/operators/ConditionalLogicalOperatorsExamples.cs#Or)]

<span data-ttu-id="2b367-108">El [operador OR lógico](or-operator.md) `|` también calcula el OR lógico de sus operandos `bool`, pero siempre evalúa ambos.</span><span class="sxs-lookup"><span data-stu-id="2b367-108">The [logical OR operator](or-operator.md) `|` also computes the logical OR of its `bool` operands, but always evaluates both operands.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="2b367-109">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="2b367-109">Operator overloadability</span></span>

<span data-ttu-id="2b367-110">Un tipo definido por el usuario no puede sobrecargar el operador OR lógico condicional.</span><span class="sxs-lookup"><span data-stu-id="2b367-110">A user-defined type cannot overload the conditional logical OR operator.</span></span> <span data-ttu-id="2b367-111">Pero si un tipo definido por el usuario sobrecarga los operadores [OR lógico](or-operator.md) y [true y false](../keywords/true-false-operators.md) de una manera determinada, la operación `||` se puede evaluar para los operandos de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="2b367-111">However, if a user-defined type overloads the [logical OR](or-operator.md) and [true and false operators](../keywords/true-false-operators.md) in a certain way, the `||` operation can be evaluated for the operands of that type.</span></span> <span data-ttu-id="2b367-112">Para obtener más información, vea la sección [Operadores lógicos condicionales definidos por el usuario](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b367-112">For more information, see the [User-defined conditional logical operators](~/_csharplang/spec/expressions.md#user-defined-conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2b367-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="2b367-113">C# language specification</span></span>

<span data-ttu-id="2b367-114">Para obtener más información, vea la sección [Operadores lógicos condicionales](~/_csharplang/spec/expressions.md#conditional-logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="2b367-114">For more information, see the [Conditional logical operators](~/_csharplang/spec/expressions.md#conditional-logical-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b367-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b367-115">See also</span></span>

- [<span data-ttu-id="2b367-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2b367-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2b367-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2b367-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2b367-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="2b367-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="2b367-119">Operador &&</span><span class="sxs-lookup"><span data-stu-id="2b367-119">&& operator</span></span>](conditional-and-operator.md)
- [<span data-ttu-id="2b367-120">Operador !</span><span class="sxs-lookup"><span data-stu-id="2b367-120">! operator</span></span>](logical-negation-operator.md)
- [<span data-ttu-id="2b367-121">Operador |</span><span class="sxs-lookup"><span data-stu-id="2b367-121">| operator</span></span>](or-operator.md)
