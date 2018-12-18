---
title: 'Operador /: Referencia de C#'
ms.custom: seodec18
ms.date: 12/13/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 45bcd64b60e7d13f389064faefeda815ea1f32c9
ms.sourcegitcommit: d6e419f9d9cd7e8f21ebf5acde6d016c16332579
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2018
ms.locfileid: "53286538"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bd51b-102">Operador / (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="bd51b-102">/ Operator (C# Reference)</span></span>

<span data-ttu-id="bd51b-103">El operador de división `/` divide su primer operando por su segundo operando.</span><span class="sxs-lookup"><span data-stu-id="bd51b-103">The division operator `/` divides its first operand by its second operand.</span></span> <span data-ttu-id="bd51b-104">Todos los tipos numéricos admiten el operador de división.</span><span class="sxs-lookup"><span data-stu-id="bd51b-104">All numeric types support the division operator.</span></span>

## <a name="integer-division"></a><span data-ttu-id="bd51b-105">División de enteros</span><span class="sxs-lookup"><span data-stu-id="bd51b-105">Integer division</span></span>

<span data-ttu-id="bd51b-106">Para los operandos de tipos enteros, el resultado del operador `/` es de un tipo entero y equivale al cociente de los dos operandos redondeados hacia cero:</span><span class="sxs-lookup"><span data-stu-id="bd51b-106">For the operands of integer types, the result of the `/` operator is of an integer type and equals the quotient of the two operands rounded towards zero:</span></span>

[!code-csharp-interactive[integer division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#Integer)]

<span data-ttu-id="bd51b-107">Para obtener el cociente de los dos operandos como número de punto flotante, use el tipo `float`, `double` o `decimal`:</span><span class="sxs-lookup"><span data-stu-id="bd51b-107">To obtain the quotient of the two operands as a floating-point number, use the `float`, `double`, or `decimal` type:</span></span>

[!code-csharp-interactive[integer as floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#IntegerAsFloatingPoint)]

## <a name="floating-point-division"></a><span data-ttu-id="bd51b-108">División de punto flotante</span><span class="sxs-lookup"><span data-stu-id="bd51b-108">Floating-point division</span></span>

<span data-ttu-id="bd51b-109">Para los tipos `float`, `double` y `decimal`, el resultado del operador `/` es el cociente de los dos operandos:</span><span class="sxs-lookup"><span data-stu-id="bd51b-109">For the `float`, `double`, and `decimal` types, the result of the `/` operator is the quotient of the two operands:</span></span>

[!code-csharp-interactive[floating-point division](~/samples/snippets/csharp/language-reference/operators/DivisionExamples.cs#FloatingPoint)]

<span data-ttu-id="bd51b-110">Si uno de los operandos es `decimal`, otro operando no puede ser `float` ni `double`, ya que ni `float` ni `double` se convierte de forma implícita a `decimal`.</span><span class="sxs-lookup"><span data-stu-id="bd51b-110">If one of the operands is `decimal`, another operand can be neither `float` nor `double`, because neither `float` nor `double` is implicitly convertible to `decimal`.</span></span> <span data-ttu-id="bd51b-111">Debe convertir explícitamente el operando `float` o `double` al tipo `decimal`.</span><span class="sxs-lookup"><span data-stu-id="bd51b-111">You must explicitly convert the `float` or `double` operand to the `decimal` type.</span></span> <span data-ttu-id="bd51b-112">Para obtener más información sobre las conversiones implícitas entre tipos numéricos, consulte [Tabla de conversiones numéricas implícitas](../keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="bd51b-112">For more information about implicit conversions between numeric types, see [Implicit numeric conversions table](../keywords/implicit-numeric-conversions-table.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="bd51b-113">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="bd51b-113">Operator overloadability</span></span>

<span data-ttu-id="bd51b-114">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `/`.</span><span class="sxs-lookup"><span data-stu-id="bd51b-114">User-defined types can [overload](../keywords/operator.md) the `/` operator.</span></span> <span data-ttu-id="bd51b-115">Cuando se sobrecarga el operador `/`, el [operador de asignación de división](division-assignment-operator.md) `/=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="bd51b-115">When the `/` operator is overloaded, the [division assignment operator](division-assignment-operator.md) `/=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bd51b-116">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="bd51b-116">C# language specification</span></span>

<span data-ttu-id="bd51b-117">Para más información, vea la sección sobre [operadores de división](~/_csharplang/spec/expressions.md#division-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="bd51b-117">For more information, see the [Division operator](~/_csharplang/spec/expressions.md#division-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd51b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd51b-118">See also</span></span>

- [<span data-ttu-id="bd51b-119">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="bd51b-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bd51b-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="bd51b-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bd51b-121">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="bd51b-121">C# Operators</span></span>](index.md)
- [<span data-ttu-id="bd51b-122">Operador %</span><span class="sxs-lookup"><span data-stu-id="bd51b-122">% Operator</span></span>](remainder-operator.md)
