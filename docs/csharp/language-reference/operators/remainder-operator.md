---
title: Operador % (Referencia de C#)
ms.date: 09/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: cd6d49b69d40f3b45aae060d46b58632dc8448f8
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144210"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6c427-102">Operador % (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6c427-102">% Operator (C# Reference)</span></span>

<span data-ttu-id="6c427-103">El operador de resto `%` calcula el resto después de dividir su primer operando entre el segundo.</span><span class="sxs-lookup"><span data-stu-id="6c427-103">The remainder operator `%` computes the remainder after dividing its first operand by its second operand.</span></span>

<span data-ttu-id="6c427-104">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `%`.</span><span class="sxs-lookup"><span data-stu-id="6c427-104">User-defined types can [overload](../keywords/operator.md) the `%` operator.</span></span> <span data-ttu-id="6c427-105">Cuando `%` está sobrecargado, el [operador de asignación de resto](remainder-assignment-operator.md) `%=` también se sobrecarga de modo implícito.</span><span class="sxs-lookup"><span data-stu-id="6c427-105">When the `%` is overloaded, the [remainder assignment operator](remainder-assignment-operator.md) `%=` is also implicitly overloaded.</span></span>

<span data-ttu-id="6c427-106">Todos los tipos numéricos admiten el operador de resto.</span><span class="sxs-lookup"><span data-stu-id="6c427-106">All numeric types support the remainder operator.</span></span>

## <a name="integer-remainder"></a><span data-ttu-id="6c427-107">Resto entero</span><span class="sxs-lookup"><span data-stu-id="6c427-107">Integer remainder</span></span>
  
<span data-ttu-id="6c427-108">En el caso de los operandos enteros, el resultado de `a % b` es el valor producido por `a - (a / b) * b`.</span><span class="sxs-lookup"><span data-stu-id="6c427-108">For the integer operands, the result of `a % b` is the value produced by `a - (a / b) * b`.</span></span> <span data-ttu-id="6c427-109">El signo de resto distinto de cero es el mismo que el del primer operando, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c427-109">The sign of the non-zero remainder is the same as that of the first operand, as the following example shows:</span></span>

[!code-csharp-interactive[integer remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#1)]

## <a name="floating-point-remainder"></a><span data-ttu-id="6c427-110">Resto de punto flotante</span><span class="sxs-lookup"><span data-stu-id="6c427-110">Floating-point remainder</span></span>

<span data-ttu-id="6c427-111">En el caso de los operandos [float](../keywords/float.md) y [double](../keywords/double.md), el resultado de `x % y` para `x` e `y` finitos es el valor `z`, de modo que</span><span class="sxs-lookup"><span data-stu-id="6c427-111">For the [float](../keywords/float.md) and [double](../keywords/double.md) operands, the result of `x % y` for the finite `x` and `y` is the value `z` such that</span></span>

- <span data-ttu-id="6c427-112">el signo de `z`, si es distinto de cero, es el mismo que el signo de `x`;</span><span class="sxs-lookup"><span data-stu-id="6c427-112">the sign of `z`, if non-zero, is the same as the sign of `x`;</span></span>
- <span data-ttu-id="6c427-113">el valor absoluto de `z` es el valor producido por `|x| - n * |y|`, donde `n` es el entero más grande posible que sea menor o igual que `|x| / |y|` y `|x|` e `|y|` son los valores absolutos de `x` e `y`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="6c427-113">the absolute value of `z` is the value produced by `|x| - n * |y|` where `n` is the largest possible integer that is less than or equal to `|x| / |y|` and `|x|` and `|y|` are the absolute values of `x` and `y`, respectively.</span></span>

<span data-ttu-id="6c427-114">Para información sobre el comportamiento del operador `%` con operandos no finitos, vea la sección [Operador de resto](~/_csharplang/spec/expressions.md#remainder-operator) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="6c427-114">For information about the behavior of the `%` operator with non-finite operands, see the [Remainder operator](~/_csharplang/spec/expressions.md#remainder-operator) section of the [C# language specification](../language-specification/index.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6c427-115">Este método de cálculo del resto es análogo al usado para los operandos enteros, pero difiere de IEEE 754.</span><span class="sxs-lookup"><span data-stu-id="6c427-115">This method of computing the remainder is analogous to that used for integer operands, but differs from the IEEE 754.</span></span> <span data-ttu-id="6c427-116">Si necesita la operación de resto conforme con IEEE 754, use el método <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c427-116">If you need the remainder operation that complies with the IEEE 754, use the <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="6c427-117">En el siguiente ejemplo se muestra el comportamiento del operador de resto de los operandos `float` y `double`:</span><span class="sxs-lookup"><span data-stu-id="6c427-117">The following example demonstrates the behavior of the remainder operator for `float` and `double` operands:</span></span>

[!code-csharp-interactive[float and double remainder](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#2)]

<span data-ttu-id="6c427-118">Observe los errores de redondeo que se pueden asociar a los tipos de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="6c427-118">Note the round-off errors that can be associated with the floating-point types.</span></span>

<span data-ttu-id="6c427-119">En el caso de los operandos [decimal](../keywords/decimal.md), el operador de resto `%` es equivalente al [operador de resto](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) del tipo <xref:System.Decimal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6c427-119">For the [decimal](../keywords/decimal.md) operands, the remainder operator `%` is equivalent to the [remainder operator](<xref:System.Decimal.op_Modulus(System.Decimal,System.Decimal)>) of the <xref:System.Decimal?displayProperty=nameWithType> type.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c427-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c427-120">See also</span></span>

- [<span data-ttu-id="6c427-121">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6c427-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6c427-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6c427-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6c427-123">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6c427-123">C# Operators</span></span>](index.md)
- <xref:System.Math.IEEERemainder%2A?displayProperty=nameWithType>
- <xref:System.Math.DivRem%2A?displayProperty=nameWithType>
