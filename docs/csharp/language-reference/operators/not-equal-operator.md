---
title: 'Operador !=: Referencia de C#'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
ms.openlocfilehash: 939b5664dba4345e62a43fb2f8d4d5379659d6aa
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610182"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3a675-102">Operador != (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3a675-102">!= Operator (C# Reference)</span></span>

<span data-ttu-id="3a675-103">El operador de desigualdad (`!=`) devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="3a675-103">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="3a675-104">Para los operandos de los [tipos integrados](../keywords/built-in-types-table.md), la expresión `x != y` genera el mismo resultado que la expresión `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="3a675-104">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="3a675-105">Para obtener más información, vea el artículo [Operador ==](equality-comparison-operator.md).</span><span class="sxs-lookup"><span data-stu-id="3a675-105">For more information, see the [== Operator](equality-comparison-operator.md) article.</span></span>

<span data-ttu-id="3a675-106">En el siguiente ejemplo se muestra el uso del operador `!=`:</span><span class="sxs-lookup"><span data-stu-id="3a675-106">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="3a675-107">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="3a675-107">Operator overloadability</span></span>

<span data-ttu-id="3a675-108">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `!=`.</span><span class="sxs-lookup"><span data-stu-id="3a675-108">User-defined types can [overload](../keywords/operator.md) the `!=` operator.</span></span> <span data-ttu-id="3a675-109">Si un tipo sobrecarga el operador de desigualdad `!=`, también debe sobrecargar el [operador de igualdad](equality-comparison-operator.md) `==`.</span><span class="sxs-lookup"><span data-stu-id="3a675-109">If a type overloads the inequality operator `!=`, it must also overload the [equality operator](equality-comparison-operator.md) `==`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3a675-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3a675-110">C# language specification</span></span>

<span data-ttu-id="3a675-111">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a675-111">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3a675-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a675-112">See also</span></span>

- [<span data-ttu-id="3a675-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3a675-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3a675-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3a675-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3a675-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="3a675-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3a675-116">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="3a675-116">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
