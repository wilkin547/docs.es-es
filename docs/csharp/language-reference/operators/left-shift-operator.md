---
title: 'Operador <<: Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- <<_CSharpKeyword
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
ms.openlocfilehash: deea2d0f720ba7f096e65c67378586bc88f24673
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219442"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8596a-102">Operador \<\< (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8596a-102">\<\< operator (C# Reference)</span></span>

<span data-ttu-id="8596a-103">El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits definido por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="8596a-103">The left-shift operator `<<` shifts its first operand left by the number of bits defined by its second operand.</span></span> <span data-ttu-id="8596a-104">Todos los tipos de enteros admiten el operador `<<`.</span><span class="sxs-lookup"><span data-stu-id="8596a-104">All integer types support the `<<` operator.</span></span> <span data-ttu-id="8596a-105">No obstante, el tipo del segundo operando debe ser [int](../keywords/int.md) o un tipo que tiene una [conversión numérica implícita predefinida](../keywords/implicit-numeric-conversions-table.md) en `int`.</span><span class="sxs-lookup"><span data-stu-id="8596a-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="8596a-106">Se descartan los bits de orden superior que están fuera del intervalo del tipo del resultado, y las posiciones de bits vacías de orden inferior se establecen en cero, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8596a-106">The high-order bits that are outside the range of the result type are discarded, and the low-order empty bit positions are set to zero, as the following example shows:</span></span>

[!code-csharp-interactive[left shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShift)]

## <a name="shift-count"></a><span data-ttu-id="8596a-107">Recuento de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="8596a-107">Shift count</span></span>

<span data-ttu-id="8596a-108">Para la expresión `x << count`, el recuento de desplazamiento real depende del tipo de `x` como sigue:</span><span class="sxs-lookup"><span data-stu-id="8596a-108">For the expression `x << count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="8596a-109">Si el tipo de `x` es [int](../keywords/int.md) o [uint](../keywords/uint.md), el valor de desplazamiento viene dado por los *cinco* bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="8596a-109">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="8596a-110">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="8596a-110">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="8596a-111">Si el tipo de `x` es [long](../keywords/long.md) o [ulong](../keywords/ulong.md), el valor de desplazamiento viene dado por los *seis* bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="8596a-111">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="8596a-112">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="8596a-112">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="8596a-113">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="8596a-113">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#LeftShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="8596a-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8596a-114">Remarks</span></span>

<span data-ttu-id="8596a-115">Las operaciones de desplazamiento nunca producen desbordamientos y generan los mismos resultados en contextos [checked y unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="8596a-115">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="8596a-116">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="8596a-116">Operator overloadability</span></span>

<span data-ttu-id="8596a-117">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `<<`.</span><span class="sxs-lookup"><span data-stu-id="8596a-117">User-defined types can [overload](../keywords/operator.md) the `<<` operator.</span></span> <span data-ttu-id="8596a-118">Si un tipo definido por el usuario `T` sobrecarga el operador `<<`, el tipo del primer operando debe ser `T` y el tipo del segundo operando debe ser `int`.</span><span class="sxs-lookup"><span data-stu-id="8596a-118">If a user-defined type `T` overloads the `<<` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="8596a-119">Cuando se sobrecarga el operador `<<`, el [operador de asignación de desplazamiento a la izquierda](left-shift-assignment-operator.md) `<<=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="8596a-119">When the `<<` operator is overloaded, the [left-shift assignment operator](left-shift-assignment-operator.md) `<<=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8596a-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8596a-120">C# language specification</span></span>

<span data-ttu-id="8596a-121">Para más información, vea la sección sobre [operadores de desplazamiento](~/_csharplang/spec/expressions.md#shift-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="8596a-121">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8596a-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8596a-122">See also</span></span>

- [<span data-ttu-id="8596a-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8596a-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8596a-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8596a-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8596a-125">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="8596a-125">C# Operators</span></span>](index.md)
- [<span data-ttu-id="8596a-126">Operador >></span><span class="sxs-lookup"><span data-stu-id="8596a-126">>> operator</span></span>](right-shift-operator.md)
