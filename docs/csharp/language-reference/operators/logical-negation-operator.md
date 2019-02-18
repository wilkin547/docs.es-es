---
title: '! operador: Referencia de C#'
ms.custom: seodec18
ms.date: 02/14/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
ms.openlocfilehash: 464bd658c9bf430191d84d3d5ad8d57173ab87c5
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303717"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="47c04-103">!</span><span class="sxs-lookup"><span data-stu-id="47c04-103">!</span></span> <span data-ttu-id="47c04-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="47c04-104">operator (C# Reference)</span></span>

<span data-ttu-id="47c04-105">El operador lógico de negación `!` es un operador unario que calcula la negación lógica de su operando [bool](../keywords/bool.md).</span><span class="sxs-lookup"><span data-stu-id="47c04-105">The logical negation operator `!` is a unary operator that computes logical negation of its [bool](../keywords/bool.md) operand.</span></span> <span data-ttu-id="47c04-106">Es decir, genera `true` si el operando es `false`, y `false` si el operando es `true`:</span><span class="sxs-lookup"><span data-stu-id="47c04-106">That is, it produces `true`, if the operand is `false`, and `false`, if the operand is `true`:</span></span>

[!code-csharp-interactive[logical negation](~/samples/snippets/csharp/language-reference/operators/LogicalNegationExamples.cs#Example)]

## <a name="operator-overloadability"></a><span data-ttu-id="47c04-107">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="47c04-107">Operator overloadability</span></span>

<span data-ttu-id="47c04-108">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `!`.</span><span class="sxs-lookup"><span data-stu-id="47c04-108">User-defined types can [overload](../keywords/operator.md) the `!` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="47c04-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="47c04-109">C# language specification</span></span>

<span data-ttu-id="47c04-110">Para más información, vea la sección sobre el [operador de negación lógica](~/_csharplang/spec/expressions.md#logical-negation-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="47c04-110">For more information, see the [Logical negation operator](~/_csharplang/spec/expressions.md#logical-negation-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="47c04-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="47c04-111">See also</span></span>

- [<span data-ttu-id="47c04-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="47c04-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47c04-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="47c04-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="47c04-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="47c04-114">C# Operators</span></span>](index.md)