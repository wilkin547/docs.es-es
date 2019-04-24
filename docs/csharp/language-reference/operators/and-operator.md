---
title: 'Operador &amp;: Referencia de C#'
ms.custom: seodec18
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: 67d60709e1c6c76071ecfb7aac74c83dec6f372a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310049"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="0063f-102">Operador &amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0063f-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="0063f-103">El operador `&` se admite de dos formas: un operador address-of unario o un operador lógico binario.</span><span class="sxs-lookup"><span data-stu-id="0063f-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="0063f-104">Operador address-of unario</span><span class="sxs-lookup"><span data-stu-id="0063f-104">Unary address-of operator</span></span>

<span data-ttu-id="0063f-105">El operador `&` unario devuelve la dirección de su operando.</span><span class="sxs-lookup"><span data-stu-id="0063f-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="0063f-106">Para obtener más información, vea [Cómo: Obtener la dirección de una variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="0063f-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="0063f-107">El operador address-of `&` requiere un contexto [no seguro](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="0063f-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="0063f-108">Operador AND bit a bit lógico entero</span><span class="sxs-lookup"><span data-stu-id="0063f-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="0063f-109">Para los tipos enteros, el operador `&` calcula el AND bit a bit lógico de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="0063f-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="0063f-110">En el ejemplo anterior se usan los literales binarios [introducidos en C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) y [mejorados en C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="0063f-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="0063f-111">Como las operaciones en tipos enteros generalmente se permiten en los tipos de enumeración, el operador `&` también es compatible con los operandos [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="0063f-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="0063f-112">Operador AND lógico booleano</span><span class="sxs-lookup"><span data-stu-id="0063f-112">Boolean logical AND operator</span></span>

<span data-ttu-id="0063f-113">Para los operandos [bool](../keywords/bool.md), el operador `&` calcula el AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="0063f-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="0063f-114">El resultado de `x & y` es `true` si tanto `x` como `y` son `true`.</span><span class="sxs-lookup"><span data-stu-id="0063f-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="0063f-115">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="0063f-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="0063f-116">El operador `&` evalúa ambos, incluso aunque el primero se evalúe como `false`, de modo que el resultado debe ser `false` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="0063f-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="0063f-117">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="0063f-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="0063f-118">El [operador AND condicional](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` también calcula el AND lógico de sus operandos, pero no evalúa el segundo operando si el primero se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="0063f-118">The [conditional AND operator](boolean-logical-operators.md#conditional-logical-and-operator-) `&&` also computes the logical AND of its operands, but doesn't evaluate the second operand if the first operand evaluates to `false`.</span></span>

<span data-ttu-id="0063f-119">Para los operandos de tipo bool que aceptan valores NULL, el comportamiento del operador `&` es coherente con la lógica de tres valores de SQL.</span><span class="sxs-lookup"><span data-stu-id="0063f-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="0063f-120">Para más información, consulte la sección [Operadores lógicos booleanos que aceptan valores NULL](boolean-logical-operators.md#nullable-boolean-logical-operators) del artículo [Operadores lógicos booleanos](boolean-logical-operators.md).</span><span class="sxs-lookup"><span data-stu-id="0063f-120">For more information, see the [Nullable Boolean logical operators](boolean-logical-operators.md#nullable-boolean-logical-operators) section of the [Boolean logical operators](boolean-logical-operators.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0063f-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="0063f-121">Operator overloadability</span></span>

<span data-ttu-id="0063f-122">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `&` binario.</span><span class="sxs-lookup"><span data-stu-id="0063f-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="0063f-123">Cuando se sobrecarga un operador `&` binario, el [operador de asignación AND](and-assignment-operator.md) `&=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="0063f-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0063f-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0063f-124">C# language specification</span></span>

<span data-ttu-id="0063f-125">Para obtener más información, vea las secciones [El operador address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) y [Operadores lógicos](~/_csharplang/spec/expressions.md#logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0063f-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0063f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="0063f-126">See also</span></span>

- [<span data-ttu-id="0063f-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0063f-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0063f-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0063f-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0063f-129">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0063f-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="0063f-130">Operadores lógicos booleanos</span><span class="sxs-lookup"><span data-stu-id="0063f-130">Boolean logical operators</span></span>](boolean-logical-operators.md)
- [<span data-ttu-id="0063f-131">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="0063f-131">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="0063f-132">Operador |</span><span class="sxs-lookup"><span data-stu-id="0063f-132">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="0063f-133">Operador ^</span><span class="sxs-lookup"><span data-stu-id="0063f-133">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="0063f-134">Operador ~</span><span class="sxs-lookup"><span data-stu-id="0063f-134">~ operator</span></span>](bitwise-complement-operator.md)
