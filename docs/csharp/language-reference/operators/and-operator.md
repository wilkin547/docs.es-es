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
ms.openlocfilehash: a799c0e37d6607e8ff72ab984ff5e540a4e11063
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236380"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="af37e-102">Operador &amp; (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="af37e-102">&amp; Operator (C# Reference)</span></span>

<span data-ttu-id="af37e-103">El operador `&` se admite de dos formas: un operador address-of unario o un operador lógico binario.</span><span class="sxs-lookup"><span data-stu-id="af37e-103">The `&` operator is supported in two forms: a unary address-of operator or a binary logical operator.</span></span>

## <a name="unary-address-of-operator"></a><span data-ttu-id="af37e-104">Operador address-of unario</span><span class="sxs-lookup"><span data-stu-id="af37e-104">Unary address-of operator</span></span>

<span data-ttu-id="af37e-105">El operador `&` unario devuelve la dirección de su operando.</span><span class="sxs-lookup"><span data-stu-id="af37e-105">The unary `&` operator returns the address of its operand.</span></span> <span data-ttu-id="af37e-106">Para obtener más información, vea [Cómo: Obtener la dirección de una variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span><span class="sxs-lookup"><span data-stu-id="af37e-106">For more information, see [How to: obtain the address of a variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).</span></span>

<span data-ttu-id="af37e-107">El operador address-of `&` requiere un contexto [no seguro](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="af37e-107">The address-of operator `&` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="integer-logical-bitwise-and-operator"></a><span data-ttu-id="af37e-108">Operador AND bit a bit lógico entero</span><span class="sxs-lookup"><span data-stu-id="af37e-108">Integer logical bitwise AND operator</span></span>

<span data-ttu-id="af37e-109">Para los tipos enteros, el operador `&` calcula el AND bit a bit lógico de sus operandos:</span><span class="sxs-lookup"><span data-stu-id="af37e-109">For integer types, the `&` operator computes the logical bitwise AND of its operands:</span></span>

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> <span data-ttu-id="af37e-110">En el ejemplo anterior se usan los literales binarios [introducidos en C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) y [mejorados en C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span><span class="sxs-lookup"><span data-stu-id="af37e-110">The preceding example uses the binary literals [introduced in C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) and [enhanced in C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).</span></span>

<span data-ttu-id="af37e-111">Como las operaciones en tipos enteros generalmente se permiten en los tipos de enumeración, el operador `&` también es compatible con los operandos [enum](../keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="af37e-111">Because operations on integer types are generally allowed on enumeration types, the `&` operator also supports [enum](../keywords/enum.md) operands.</span></span>

## <a name="boolean-logical-and-operator"></a><span data-ttu-id="af37e-112">Operador AND lógico booleano</span><span class="sxs-lookup"><span data-stu-id="af37e-112">Boolean logical AND operator</span></span>

<span data-ttu-id="af37e-113">Para los operandos [bool](../keywords/bool.md), el operador `&` calcula el AND lógico de sus operandos.</span><span class="sxs-lookup"><span data-stu-id="af37e-113">For [bool](../keywords/bool.md) operands, the `&` operator computes the logical AND of its operands.</span></span> <span data-ttu-id="af37e-114">El resultado de `x & y` es `true` si tanto `x` como `y` son `true`.</span><span class="sxs-lookup"><span data-stu-id="af37e-114">The result of `x & y` is `true` if both `x` and `y` are `true`.</span></span> <span data-ttu-id="af37e-115">De lo contrario, el resultado es `false`.</span><span class="sxs-lookup"><span data-stu-id="af37e-115">Otherwise, the result is `false`.</span></span>

<span data-ttu-id="af37e-116">El operador `&` evalúa ambos, incluso aunque el primero se evalúe como `false`, de modo que el resultado debe ser `false` con independencia del valor del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="af37e-116">The `&` operator evaluates both operands even if the first operand evaluates to `false`, so that the result must be `false` regardless of the value of the second operand.</span></span> <span data-ttu-id="af37e-117">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="af37e-117">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

<span data-ttu-id="af37e-118">El [operador AND condicional](conditional-and-operator.md) `&&` también calcula el AND lógico de sus operandos, pero evalúa el segundo operando solo si el primero se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="af37e-118">The [conditional AND operator](conditional-and-operator.md) `&&` also computes the logical AND of its operands, but evaluates the second operand only if the first operand evaluates to `true`.</span></span>

<span data-ttu-id="af37e-119">Para los operandos de tipo bool que aceptan valores NULL, el comportamiento del operador `&` es coherente con la lógica de tres valores de SQL.</span><span class="sxs-lookup"><span data-stu-id="af37e-119">For nullable bool operands, the behavior of the `&` operator is consistent with SQL's three-valued logic.</span></span> <span data-ttu-id="af37e-120">Para obtener más información, vea la sección [Tipo bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) del artículo [Uso de tipos que aceptan valores NULL](../../programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="af37e-120">For more information, see the [The bool? type](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) section of the [Using nullable types](../../programming-guide/nullable-types/using-nullable-types.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="af37e-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="af37e-121">Operator overloadability</span></span>

<span data-ttu-id="af37e-122">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `&` binario.</span><span class="sxs-lookup"><span data-stu-id="af37e-122">User-defined types can [overload](../keywords/operator.md) the binary `&` operator.</span></span> <span data-ttu-id="af37e-123">Cuando se sobrecarga un operador `&` binario, el [operador de asignación AND](and-assignment-operator.md) `&=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="af37e-123">When a binary `&` operator is overloaded, the [AND assignment operator](and-assignment-operator.md) `&=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="af37e-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="af37e-124">C# language specification</span></span>

<span data-ttu-id="af37e-125">Para obtener más información, vea las secciones [El operador address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) y [Operadores lógicos](~/_csharplang/spec/expressions.md#logical-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="af37e-125">For more information, see [The address-of operator](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) and [Logical operators](~/_csharplang/spec/expressions.md#logical-operators) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="af37e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="af37e-126">See also</span></span>

- [<span data-ttu-id="af37e-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="af37e-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="af37e-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="af37e-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="af37e-129">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="af37e-129">C# Operators</span></span>](index.md)
- [<span data-ttu-id="af37e-130">Tipos de puntero</span><span class="sxs-lookup"><span data-stu-id="af37e-130">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="af37e-131">Operador |</span><span class="sxs-lookup"><span data-stu-id="af37e-131">| operator</span></span>](or-operator.md)
- [<span data-ttu-id="af37e-132">Operador ^</span><span class="sxs-lookup"><span data-stu-id="af37e-132">^ operator</span></span>](xor-operator.md)
- [<span data-ttu-id="af37e-133">Operador ~</span><span class="sxs-lookup"><span data-stu-id="af37e-133">~ operator</span></span>](bitwise-complement-operator.md)
- [<span data-ttu-id="af37e-134">Operador &&</span><span class="sxs-lookup"><span data-stu-id="af37e-134">&& operator</span></span>](conditional-and-operator.md)
