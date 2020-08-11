---
title: Operadores de comparación (referencia de C#)
description: Obtenga información sobre los operadores de comparación de C# que puede usar para comprobar el orden de los valores numéricos.
ms.date: 05/11/2020
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
ms.openlocfilehash: 9fa739d8b5461d4043f3ae51f5d14949a95c68e5
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87916883"
---
# <a name="comparison-operators-c-reference"></a><span data-ttu-id="343f8-103">Operadores de comparación (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="343f8-103">Comparison operators (C# reference)</span></span>

<span data-ttu-id="343f8-104">Los operadores de la comparación [`<` (menor que)](#less-than-operator-), [`>` (mayor que)](#greater-than-operator-), [`<=` (menor o igual que)](#less-than-or-equal-operator-) y [`>=` (mayor o igual que)](#greater-than-or-equal-operator-), también conocidos como relacionales, comparan sus operandos.</span><span class="sxs-lookup"><span data-stu-id="343f8-104">The [`<` (less than)](#less-than-operator-), [`>` (greater than)](#greater-than-operator-), [`<=` (less than or equal)](#less-than-or-equal-operator-), and [`>=` (greater than or equal)](#greater-than-or-equal-operator-) comparison, also known as relational, operators compare their operands.</span></span> <span data-ttu-id="343f8-105">Estos operadores se admiten en todos los tipos numéricos [enteros](../builtin-types/integral-numeric-types.md) y de [punto flotante](../builtin-types/floating-point-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="343f8-105">Those operators are supported by all [integral](../builtin-types/integral-numeric-types.md) and [floating-point](../builtin-types/floating-point-numeric-types.md) numeric types.</span></span>

> [!NOTE]
> <span data-ttu-id="343f8-106">Para los operadores `==`, `<`, `>`, `<=` y `>=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`.</span><span class="sxs-lookup"><span data-stu-id="343f8-106">For the `==`, `<`, `>`, `<=`, and `>=` operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="343f8-107">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`.</span><span class="sxs-lookup"><span data-stu-id="343f8-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="343f8-108">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="343f8-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="343f8-109">El tipo [char](../builtin-types/char.md) también admite operadores de comparación.</span><span class="sxs-lookup"><span data-stu-id="343f8-109">The [char](../builtin-types/char.md) type also supports comparison operators.</span></span> <span data-ttu-id="343f8-110">En el caso de los operandos `char`, se comparan los códigos de caracteres correspondientes.</span><span class="sxs-lookup"><span data-stu-id="343f8-110">In the case of `char` operands, the corresponding character codes are compared.</span></span>

<span data-ttu-id="343f8-111">Los tipos de enumeración también admiten operadores de comparación.</span><span class="sxs-lookup"><span data-stu-id="343f8-111">Enumeration types also support comparison operators.</span></span> <span data-ttu-id="343f8-112">Para los operandos del mismo tipo [enum](../builtin-types/enum.md), se comparan los valores correspondientes del tipo entero subyacente.</span><span class="sxs-lookup"><span data-stu-id="343f8-112">For operands of the same [enum](../builtin-types/enum.md) type, the corresponding values of the underlying integral type are compared.</span></span>

<span data-ttu-id="343f8-113">Los [operadores `==` y `!=`](equality-operators.md) comprueban si los operandos son iguales.</span><span class="sxs-lookup"><span data-stu-id="343f8-113">The [`==` and `!=` operators](equality-operators.md) check if their operands are equal or not.</span></span>

## <a name="less-than-operator-"></a><span data-ttu-id="343f8-114">Operador menor que \<</span><span class="sxs-lookup"><span data-stu-id="343f8-114">Less than operator \<</span></span>

<span data-ttu-id="343f8-115">El operador `<` devuelve `true` si el operando izquierdo es menor que el derecho; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="343f8-115">The `<` operator returns `true` if its left-hand operand is less than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than example](snippets/shared/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a><span data-ttu-id="343f8-116">Operador mayor que ></span><span class="sxs-lookup"><span data-stu-id="343f8-116">Greater than operator ></span></span>

<span data-ttu-id="343f8-117">El operador `>` devuelve `true` si el operando izquierdo es mayor que el derecho; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="343f8-117">The `>` operator returns `true` if its left-hand operand is greater than its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than example](snippets/shared/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a><span data-ttu-id="343f8-118">Operador menor o igual que \<=</span><span class="sxs-lookup"><span data-stu-id="343f8-118">Less than or equal operator \<=</span></span>

<span data-ttu-id="343f8-119">El operador `<=` devuelve `true` si el operando izquierdo es menor o igual que el derecho; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="343f8-119">The `<=` operator returns `true` if its left-hand operand is less than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[less than or equal example](snippets/shared/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a><span data-ttu-id="343f8-120">Operador mayor o igual que >=</span><span class="sxs-lookup"><span data-stu-id="343f8-120">Greater than or equal operator >=</span></span>

<span data-ttu-id="343f8-121">El operador `>=` devuelve `true` si el operando izquierdo es mayor o igual que el derecho; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="343f8-121">The `>=` operator returns `true` if its left-hand operand is greater than or equal to its right-hand operand, `false` otherwise:</span></span>

[!code-csharp-interactive[greater than or equal example](snippets/shared/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a><span data-ttu-id="343f8-122">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="343f8-122">Operator overloadability</span></span>

<span data-ttu-id="343f8-123">Un tipo definido por el usuario puede [sobrecargar](operator-overloading.md) los operadores `<`, `>`, `<=` y `>=`.</span><span class="sxs-lookup"><span data-stu-id="343f8-123">A user-defined type can [overload](operator-overloading.md) the `<`, `>`, `<=`, and `>=` operators.</span></span>

<span data-ttu-id="343f8-124">Si un tipo sobrecarga uno de los operadores `<` o `>`, también debe sobrecargar `<` y `>`.</span><span class="sxs-lookup"><span data-stu-id="343f8-124">If a type overloads one of the `<` or `>` operators, it must overload both `<` and `>`.</span></span> <span data-ttu-id="343f8-125">Si un tipo sobrecarga uno de los operadores `<=` o `>=`, también debe sobrecargar `<=` y `>=`.</span><span class="sxs-lookup"><span data-stu-id="343f8-125">If a type overloads one of the `<=` or `>=` operators, it must overload both `<=` and `>=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="343f8-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="343f8-126">C# language specification</span></span>

<span data-ttu-id="343f8-127">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="343f8-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="343f8-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="343f8-128">See also</span></span>

- [<span data-ttu-id="343f8-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="343f8-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="343f8-130">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="343f8-130">C# operators and expressions</span></span>](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [<span data-ttu-id="343f8-131">Operadores de igualdad</span><span class="sxs-lookup"><span data-stu-id="343f8-131">Equality operators</span></span>](equality-operators.md)
