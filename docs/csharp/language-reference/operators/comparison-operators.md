---
title: 'Operadores de comparación: referencia de C#'
description: Obtenga información sobre los operadores de comparación de C# que puede usar para comprobar el orden de los valores numéricos.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 6d3751ff1ee2c6ee2f058eeda4ffd5db188a988e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633760"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="4aad3-103">Operadores de comparación (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4aad3-103">Comparison operators (C# Reference)</span></span>

<span data-ttu-id="4aad3-104">Los operadores de la comparación [`<` (menor que)](#less-than-operator-), [`>` (mayor que)](#greater-than-operator-), [`<=` (menor o igual que)](#less-than-or-equal-operator-) y [`>=` (mayor o igual que)](#greater-than-or-equal-operator-), también conocidos como relacionales, comparan sus operandos.</span><span class="sxs-lookup"><span data-stu-id="4aad3-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="4aad3-105">Estos operadores admiten todos los tipos numéricos [integrales](../keywords/integral-types-table.md) y de [punto flotante](../keywords/floating-point-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="4aad3-105">Those operators support all [integral](../keywords/integral-types-table.md) and [floating-point](../keywords/floating-point-types-table.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="4aad3-106">Para los operadores `==`, `<`, `>`, `<=` y `>=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="4aad3-107">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="4aad3-108">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4aad3-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="4aad3-109">Los tipos de enumeración también admiten operadores de comparación.</span><span class="sxs-lookup"><span data-stu-id="4aad3-109">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="4aad3-110">Para los operandos del mismo tipo [enum](../keywords/enum.md), se comparan los valores correspondientes del tipo entero subyacente.</span><span class="sxs-lookup"><span data-stu-id="4aad3-110">For operands of the same [enum](../keywords/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="4aad3-111">Los [operadores `==` y `!=`](equality-operators.md) comprueban si los operandos son iguales.</span><span class="sxs-lookup"><span data-stu-id="4aad3-111">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="4aad3-112">Operador menor que \<</span><span class="sxs-lookup"><span data-stu-id="4aad3-112">Less than operator \<</span></span>

<span data-ttu-id="4aad3-113">El operador `<` devuelve `true` si su primer operando es menor que el segundo; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-113">The `<` operator returns `true` if its first operand is less than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="4aad3-114">Operador mayor que ></span><span class="sxs-lookup"><span data-stu-id="4aad3-114">Greater than operator ></span></span>

<span data-ttu-id="4aad3-115">El operador `>` devuelve `true` si su primer operando es mayor que el segundo; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-115">The `>` operator returns `true` if its first operand is greater than its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="4aad3-116">Operador menor o igual que \<=</span><span class="sxs-lookup"><span data-stu-id="4aad3-116">Less than or equal operator \<=</span></span>

<span data-ttu-id="4aad3-117">El operador `<=` devuelve `true` si su primer operando es menor o igual que el segundo; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-117">The `<=` operator returns `true` if its first operand is less than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="4aad3-118">Operador mayor o igual que >=</span><span class="sxs-lookup"><span data-stu-id="4aad3-118">Greater than or equal operator >=</span></span>

<span data-ttu-id="4aad3-119">El operador `>=` devuelve `true` si su primer operando es mayor o igual que el segundo; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-119">The `>=` operator returns `true` if its first operand is greater than or equal to its second operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](~/samples/snippets/csharp/language-reference/operators/GreaterAndLessOperatorsExamples.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="4aad3-120">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="4aad3-120">Operator overloadability</span></span>

<span data-ttu-id="4aad3-121">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `<`, `>`, `<=` y `>=`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-121">A user-defined type can [overload](../keywords/operator.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="4aad3-122">Si un tipo sobrecarga uno de los operadores `<` o `>`, también debe sobrecargar `<` y `>`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-122">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="4aad3-123">Si un tipo sobrecarga uno de los operadores `<=` o `>=`, también debe sobrecargar `<=` y `>=`.</span><span class="sxs-lookup"><span data-stu-id="4aad3-123">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4aad3-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4aad3-124">C# language specification</span></span>

<span data-ttu-id="4aad3-125">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4aad3-125">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4aad3-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4aad3-126">See also</span></span>

- [<span data-ttu-id="4aad3-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4aad3-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4aad3-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4aad3-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4aad3-129">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4aad3-129">C# Operators</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="4aad3-130">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="4aad3-130">Equality operators</span></span>](equality-operators.md)
