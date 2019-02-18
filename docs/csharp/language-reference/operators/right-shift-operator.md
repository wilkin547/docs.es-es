---
title: '>> : Referencia de C#'
ms.custom: seodec18
ms.date: 02/12/2019
f1_keywords:
- '>>_CSharpKeyword'
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
ms.openlocfilehash: 809cd2cab29d3378892ea224cf846e9d0909b073
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219729"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0bef6-102">Operador >> (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0bef6-102">>> operator (C# Reference)</span></span>

<span data-ttu-id="0bef6-103">El operador de desplazamiento a la derecha `>>` desplaza su primer operando a la derecha el número de bits definido por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="0bef6-103">The right-shift operator `>>` shifts its first operand right by the number of bits defined by its second operand.</span></span> <span data-ttu-id="0bef6-104">Todos los tipos de enteros admiten el operador `>>`.</span><span class="sxs-lookup"><span data-stu-id="0bef6-104">All integer types support the `>>` operator.</span></span> <span data-ttu-id="0bef6-105">No obstante, el tipo del segundo operando debe ser [int](../keywords/int.md) o un tipo que tiene una [conversión numérica implícita predefinida](../keywords/implicit-numeric-conversions-table.md) en `int`.</span><span class="sxs-lookup"><span data-stu-id="0bef6-105">However, the type of the second operand must be [int](../keywords/int.md) or a type that has a [predefined implicit numeric conversion](../keywords/implicit-numeric-conversions-table.md) to `int`.</span></span>

<span data-ttu-id="0bef6-106">La operación de desplazamiento a la derecha descarta los bits de orden inferior.</span><span class="sxs-lookup"><span data-stu-id="0bef6-106">The right-shift operation discards the low-order bits.</span></span> <span data-ttu-id="0bef6-107">Las posiciones de bits vacíos de orden superior se establecen basándose en el tipo del primer operando como sigue:</span><span class="sxs-lookup"><span data-stu-id="0bef6-107">The high-order empty bit positions are set based on the type of the first operand as follows:</span></span>

- <span data-ttu-id="0bef6-108">Si el primer operando es de tipo [int](../keywords/int.md) o [long](../keywords/long.md), el operador de desplazamiento a la derecha realiza un desplazamiento **aritmético**: el valor del bit más significativo (el bit de signo) del primer operando se propaga a las posiciones de bits vacíos de orden superior.</span><span class="sxs-lookup"><span data-stu-id="0bef6-108">If the first operand is of type [int](../keywords/int.md) or [long](../keywords/long.md), the right-shift operator performs an **arithmetic** shift: the value of the most significant bit (the sign bit) of the first operand is propagated to the high-order empty bit positions.</span></span> <span data-ttu-id="0bef6-109">Es decir, las posiciones de bits vacíos de orden superior se establecen en cero si el primer operando no es negativo y se establecen en uno si es negativo.</span><span class="sxs-lookup"><span data-stu-id="0bef6-109">That is, the high-order empty bit positions are set to zero if the first operand is non-negative and set to one if it's negative.</span></span>

- <span data-ttu-id="0bef6-110">Si el primer operando es de tipo [uint](../keywords/uint.md) o [ulong](../keywords/ulong.md), el operador de desplazamiento a la derecha realiza un desplazamiento **lógico**: las posiciones de bits vacíos de orden superior se establecen siempre en cero.</span><span class="sxs-lookup"><span data-stu-id="0bef6-110">If the first operand is of type [uint](../keywords/uint.md) or [ulong](../keywords/ulong.md), the right-shift operator performs a **logical** shift: the high-order empty bit positions are always set to zero.</span></span>

<span data-ttu-id="0bef6-111">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="0bef6-111">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[right shift example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShift)]

## <a name="shift-count"></a><span data-ttu-id="0bef6-112">Recuento de desplazamiento</span><span class="sxs-lookup"><span data-stu-id="0bef6-112">Shift count</span></span>

<span data-ttu-id="0bef6-113">Para la expresión `x >> count`, el recuento de desplazamiento real depende del tipo de `x` como sigue:</span><span class="sxs-lookup"><span data-stu-id="0bef6-113">For the expression `x >> count`, the actual shift count depends on the type of `x` as follows:</span></span>

- <span data-ttu-id="0bef6-114">Si el tipo de `x` es [int](../keywords/int.md) o [uint](../keywords/uint.md), el valor de desplazamiento viene dado por los *cinco* bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="0bef6-114">If the type of `x` is [int](../keywords/int.md) or [uint](../keywords/uint.md), the shift count is given by the low-order *five* bits of the second operand.</span></span> <span data-ttu-id="0bef6-115">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x1F` (o `count & 0b_1_1111`).</span><span class="sxs-lookup"><span data-stu-id="0bef6-115">That is, the shift count is computed from `count & 0x1F` (or `count & 0b_1_1111`).</span></span>

- <span data-ttu-id="0bef6-116">Si el tipo de `x` es [long](../keywords/long.md) o [ulong](../keywords/ulong.md), el valor de desplazamiento viene dado por los *seis* bits de orden inferior del segundo operando.</span><span class="sxs-lookup"><span data-stu-id="0bef6-116">If the type of `x` is [long](../keywords/long.md) or [ulong](../keywords/ulong.md), the shift count is given by the low-order *six* bits of the second operand.</span></span> <span data-ttu-id="0bef6-117">Es decir, el valor de desplazamiento se calcula a partir de `count & 0x3F` (o `count & 0b_11_1111`).</span><span class="sxs-lookup"><span data-stu-id="0bef6-117">That is, the shift count is computed from `count & 0x3F` (or `count & 0b_11_1111`).</span></span>

<span data-ttu-id="0bef6-118">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="0bef6-118">The following example demonstrates that behavior:</span></span>

[!code-csharp-interactive[shift count example](~/samples/snippets/csharp/language-reference/operators/ShiftOperatorsExamples.cs#RightShiftByLargeCount)]

## <a name="remarks"></a><span data-ttu-id="0bef6-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0bef6-119">Remarks</span></span>

<span data-ttu-id="0bef6-120">Las operaciones de desplazamiento nunca producen desbordamientos y generan los mismos resultados en contextos [checked y unchecked](../keywords/checked-and-unchecked.md).</span><span class="sxs-lookup"><span data-stu-id="0bef6-120">Shift operations never cause overflows and produce the same results in [checked and unchecked](../keywords/checked-and-unchecked.md) contexts.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="0bef6-121">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="0bef6-121">Operator overloadability</span></span>

<span data-ttu-id="0bef6-122">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `>>`.</span><span class="sxs-lookup"><span data-stu-id="0bef6-122">User-defined types can [overload](../keywords/operator.md) the `>>` operator.</span></span> <span data-ttu-id="0bef6-123">Si un tipo definido por el usuario `T` sobrecarga el operador `>>`, el tipo del primer operando debe ser `T` y el tipo del segundo operando debe ser `int`.</span><span class="sxs-lookup"><span data-stu-id="0bef6-123">If a user-defined type `T` overloads the `>>` operator, the type of the first operand must be `T` and the type of the second operand must be `int`.</span></span> <span data-ttu-id="0bef6-124">Cuando se sobrecarga el operador `>>`, el [operador de asignación de desplazamiento a la derecha](right-shift-assignment-operator.md) `>>=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="0bef6-124">When the `>>` operator is overloaded, the [right-shift assignment operator](right-shift-assignment-operator.md) `>>=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0bef6-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0bef6-125">C# language specification</span></span>

<span data-ttu-id="0bef6-126">Para más información, vea la sección sobre [operadores de desplazamiento](~/_csharplang/spec/expressions.md#shift-operators) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0bef6-126">For more information, see the [Shift operators](~/_csharplang/spec/expressions.md#shift-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0bef6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0bef6-127">See also</span></span>

- [<span data-ttu-id="0bef6-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0bef6-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0bef6-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0bef6-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0bef6-130">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="0bef6-130">C# operators</span></span>](index.md)
- [<span data-ttu-id="0bef6-131">Operador <<</span><span class="sxs-lookup"><span data-stu-id="0bef6-131"><< operator</span></span>](left-shift-operator.md)