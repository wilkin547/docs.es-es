---
title: 'Operador &gt;=: Referencia de C#'
ms.custom: seodec18
ms.date: 12/18/2018
f1_keywords:
- '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
ms.openlocfilehash: 34437742d33cff97e53c6dfb163df083e80d41f3
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655938"
---
# <a name="gt-operator-c-reference"></a><span data-ttu-id="e25cf-102">Operador &gt;= (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e25cf-102">&gt;= Operator (C# Reference)</span></span>

<span data-ttu-id="e25cf-103">El operador relacional "mayor o igual que" `>=` devuelve `true` si su primer operando es mayor o igual que el segundo; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-103">The "greater than or equal" relational operator `>=` returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise.</span></span> <span data-ttu-id="e25cf-104">Todos los valores numéricos y los tipos de enumeración admiten el operador `>=`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-104">All numeric and  enumeration types support the `>=` operator.</span></span> <span data-ttu-id="e25cf-105">Para los operandos del mismo tipo [enum](../keywords/enum.md), se comparan los valores correspondientes del tipo entero subyacente.</span><span class="sxs-lookup"><span data-stu-id="e25cf-105">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

> [!NOTE]
> <span data-ttu-id="e25cf-106">Para los operadores relacionales `==`, `>`, `<`, `>=` y `<=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="e25cf-107">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="e25cf-108">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e25cf-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="e25cf-109">En el siguiente ejemplo se muestra el uso del operador `>=`:</span><span class="sxs-lookup"><span data-stu-id="e25cf-109">The following example demonstrates the usage of the `>=` operator:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="e25cf-110">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="e25cf-110">Operator overloadability</span></span>

<span data-ttu-id="e25cf-111">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `>=`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-111">User-defined types can [overload](../keywords/operator.md) the `>=` operator.</span></span> <span data-ttu-id="e25cf-112">Si un tipo sobrecarga el operador "mayor o igual que" `>=`, también debe sobrecargar el [operador "menor o igual que"](less-than-equal-operator.md) `<=`.</span><span class="sxs-lookup"><span data-stu-id="e25cf-112">If a type overloads the "greater than or equal" operator `>=`, it must also overload the ["less than or equal" operator](less-than-equal-operator.md) `<=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e25cf-113">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="e25cf-113">C# language specification</span></span>

<span data-ttu-id="e25cf-114">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="e25cf-114">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e25cf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e25cf-115">See also</span></span>

- [<span data-ttu-id="e25cf-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e25cf-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e25cf-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e25cf-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e25cf-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="e25cf-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="e25cf-119">Operador ></span><span class="sxs-lookup"><span data-stu-id="e25cf-119">> Operator</span></span>](greater-than-operator.md)
- [<span data-ttu-id="e25cf-120">Operador ==</span><span class="sxs-lookup"><span data-stu-id="e25cf-120">== Operator</span></span>](equality-comparison-operator.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
