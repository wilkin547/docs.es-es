---
title: + Operador (Referencia de C#)
ms.date: 10/22/2018
f1_keywords:
- +_CSharpKeyword
helpviewer_keywords:
- + operator [C#]
- concatenation operator [C#]
- addition operator [C#]
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
ms.openlocfilehash: 27ea47d698b20f112880750ec0bc931f1917f142
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50192309"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="60db4-102">Operador + (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="60db4-102">+ Operator (C# Reference)</span></span>

<span data-ttu-id="60db4-103">El operador `+` se admite de dos formas: un operador más unario o un operador de suma binario.</span><span class="sxs-lookup"><span data-stu-id="60db4-103">The `+` operator is supported in two forms: a unary plus operator or a binary addition operator.</span></span>

## <a name="unary-plus-operator"></a><span data-ttu-id="60db4-104">Operador unario más</span><span class="sxs-lookup"><span data-stu-id="60db4-104">Unary plus operator</span></span>

<span data-ttu-id="60db4-105">El operador `+` unario devuelve el valor de su operando.</span><span class="sxs-lookup"><span data-stu-id="60db4-105">The unary `+` operator returns the value of its operand.</span></span> <span data-ttu-id="60db4-106">Es compatible con todos los tipos numéricos.</span><span class="sxs-lookup"><span data-stu-id="60db4-106">It's supported by all numeric types.</span></span>

## <a name="numeric-addition"></a><span data-ttu-id="60db4-107">Suma de números</span><span class="sxs-lookup"><span data-stu-id="60db4-107">Numeric addition</span></span>

<span data-ttu-id="60db4-108">Para tipos numéricos, el operador `+` calcula la suma de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="60db4-108">For numeric types, the `+` operator computes the sum of its operands:</span></span>

[!code-csharp-interactive[numeric addition](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddNumerics)]

## <a name="string-concatenation"></a><span data-ttu-id="60db4-109">Concatenación de cadenas</span><span class="sxs-lookup"><span data-stu-id="60db4-109">String concatenation</span></span>

<span data-ttu-id="60db4-110">Cuando uno o ambos operandos son de tipo [cadena](../keywords/string.md), el operador `+` concatena las representaciones de cadena de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="60db4-110">When one or both operands are of type [string](../keywords/string.md), the `+` operator concatenates the string representations of its operands:</span></span>

[!code-csharp-interactive[string concatenation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddStrings)]

<span data-ttu-id="60db4-111">A partir de C# 6, la [interpolación de cadenas](../tokens/interpolated.md) proporciona una manera más conveniente de dar formato a las cadenas:</span><span class="sxs-lookup"><span data-stu-id="60db4-111">Starting with C# 6, [string interpolation](../tokens/interpolated.md) provides a more convenient way to format strings:</span></span>

[!code-csharp-interactive[string interpolation](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#UseStringInterpolation)]

## <a name="delegate-combination"></a><span data-ttu-id="60db4-112">Combinación de delegados</span><span class="sxs-lookup"><span data-stu-id="60db4-112">Delegate combination</span></span>

<span data-ttu-id="60db4-113">Para los tipos de [delegado](../keywords/delegate.md), el operador `+` devuelve una nueva instancia de delegado que, cuando se invoca, invoca el primer operando y luego invoca el segundo operando.</span><span class="sxs-lookup"><span data-stu-id="60db4-113">For [delegate](../keywords/delegate.md) types, the `+` operator returns a new delegate instance that, when invoked, invokes the first operand and then invokes the second operand.</span></span> <span data-ttu-id="60db4-114">Si alguno de los operandos es `null`, el operador `+` devuelve el valor del otro operando (que también podría ser `null`).</span><span class="sxs-lookup"><span data-stu-id="60db4-114">If any of the operands is `null`, the `+` operator returns the value of another operand (which also might be `null`).</span></span> <span data-ttu-id="60db4-115">El ejemplo siguiente muestra cómo los delegados se pueden combinar con el operador `+`:</span><span class="sxs-lookup"><span data-stu-id="60db4-115">The following example shows how delegates can be combined with the `+` operator:</span></span>

[!code-csharp-interactive[delegate combination](~/samples/snippets/csharp/language-reference/operators/AdditionExamples.cs#AddDelegates)]

<span data-ttu-id="60db4-116">Para más información sobre los tipos de delegado, vea [Delegados](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="60db4-116">For more information about delegate types, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="60db4-117">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="60db4-117">Operator overloadability</span></span>

<span data-ttu-id="60db4-118">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) los operadores unarios y binarios `+`.</span><span class="sxs-lookup"><span data-stu-id="60db4-118">User-defined types can [overload](../keywords/operator.md) the unary and binary `+` operators.</span></span> <span data-ttu-id="60db4-119">Cuando se sobrecarga un operador `+` binario, el [operador de asignación de suma](addition-assignment-operator.md) `+=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="60db4-119">When a binary `+` operator is overloaded, the [addition assignment operator](addition-assignment-operator.md) `+=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="60db4-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="60db4-120">C# language specification</span></span>

<span data-ttu-id="60db4-121">Para más información, consulte las secciones [Operador unario más](~/_csharplang/spec/expressions.md#unary-plus-operator) y [Operador de suma](~/_csharplang/spec/expressions.md#addition-operator) de la [especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="60db4-121">For more information, see the [Unary plus operator](~/_csharplang/spec/expressions.md#unary-plus-operator) and [Addition operator](~/_csharplang/spec/expressions.md#addition-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60db4-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="60db4-122">See also</span></span>

- [<span data-ttu-id="60db4-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="60db4-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="60db4-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="60db4-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="60db4-125">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="60db4-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="60db4-126">Interpolación de cadenas</span><span class="sxs-lookup"><span data-stu-id="60db4-126">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="60db4-127">Cómo: Concatenar varias cadenas</span><span class="sxs-lookup"><span data-stu-id="60db4-127">How to: Concatenate Multiple Strings</span></span>](../../how-to/concatenate-multiple-strings.md)
- [<span data-ttu-id="60db4-128">Delegados</span><span class="sxs-lookup"><span data-stu-id="60db4-128">Delegates</span></span>](../../programming-guide/delegates/index.md)
- [<span data-ttu-id="60db4-129">Checked y unchecked</span><span class="sxs-lookup"><span data-stu-id="60db4-129">Checked and unchecked</span></span>](../keywords/checked-and-unchecked.md)
