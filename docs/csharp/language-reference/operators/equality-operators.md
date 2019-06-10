---
title: 'Operadores de igualdad: referencia de C#'
description: Obtenga información sobre los operadores de comparación de igualdad de C#
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 3b2aeceae8371f0728da2bcebbbe597ee135f256
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758265"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="4a5be-103">Operadores de igualdad (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4a5be-103">Equality operators (C# Reference)</span></span>

<span data-ttu-id="4a5be-104">Los operadores [`==` (igualdad)](#equality-operator-) y [`!=` (desigualdad)](#inequality-operator-) comprueban si los operandos son iguales.</span><span class="sxs-lookup"><span data-stu-id="4a5be-104">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="4a5be-105">Operador de igualdad ==</span><span class="sxs-lookup"><span data-stu-id="4a5be-105">Equality operator ==</span></span>

<span data-ttu-id="4a5be-106">El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-106">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="4a5be-107">Igualdad entre tipos de valor</span><span class="sxs-lookup"><span data-stu-id="4a5be-107">Value types equality</span></span>

<span data-ttu-id="4a5be-108">Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:</span><span class="sxs-lookup"><span data-stu-id="4a5be-108">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="4a5be-109">Para los operadores `==`, [`<`, `>`, `<=` y `>=`](comparison-operators.md), si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-109">For the `==`, [`<`, `>`, `<=`, and `>=`](comparison-operators.md) operators, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="4a5be-110">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-110">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="4a5be-111">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4a5be-111">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="4a5be-112">Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.</span><span class="sxs-lookup"><span data-stu-id="4a5be-112">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="4a5be-113">Los tipos [struct](../keywords/struct.md) definidos por el usuario no son compatibles con el operador `==` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4a5be-113">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="4a5be-114">Para admitir el operador `==`, un elemento struct definido por el usuario debe [sobrecargarlo](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="4a5be-114">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="4a5be-115">A partir de C# 7.3, los operadores `==` y `!=` son compatibles con las [tuplas](../../tuples.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="4a5be-115">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="4a5be-116">Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="4a5be-116">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="4a5be-117">Igualdad entre cadenas</span><span class="sxs-lookup"><span data-stu-id="4a5be-117">String equality</span></span>

<span data-ttu-id="4a5be-118">Dos operandos [string](../keywords/string.md) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:</span><span class="sxs-lookup"><span data-stu-id="4a5be-118">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#StringEquality)]

<span data-ttu-id="4a5be-119">Es la comparación de ordinales que distingue entre mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4a5be-119">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="4a5be-120">Para obtener más información sobre la comparación de cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="4a5be-120">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="4a5be-121">Igualdad entre tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="4a5be-121">Reference types equality</span></span>

<span data-ttu-id="4a5be-122">Dos operandos de tipos de referencia (excepto `string`) son iguales si hacen referencia al mismo objeto:</span><span class="sxs-lookup"><span data-stu-id="4a5be-122">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/csharp/language-reference/operators/EqualityOperators.cs#ReferenceTypesEquality)]

<span data-ttu-id="4a5be-123">Como se muestra en el ejemplo, el operador `==` es compatible de forma predeterminada con los tipos de referencia definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4a5be-123">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="4a5be-124">Sin embargo, un tipo de referencia definido por el usuario puede sobrecargar el operador `==`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-124">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="4a5be-125">Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="4a5be-125">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="4a5be-126">Operador de desigualdad !=</span><span class="sxs-lookup"><span data-stu-id="4a5be-126">Inequality operator !=</span></span>

<span data-ttu-id="4a5be-127">El operador de desigualdad (`!=`) devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-127">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="4a5be-128">Para los operandos de los [tipos integrados](../keywords/built-in-types-table.md), la expresión `x != y` genera el mismo resultado que la expresión `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-128">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="4a5be-129">Para obtener más información sobre la igualdad de tipos, vea la sección [Operador de igualdad](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="4a5be-129">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="4a5be-130">En el siguiente ejemplo se muestra el uso del operador `!=`:</span><span class="sxs-lookup"><span data-stu-id="4a5be-130">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/csharp/language-reference/operators/EqualityOperators.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="4a5be-131">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="4a5be-131">Operator overloadability</span></span>

<span data-ttu-id="4a5be-132">Un tipo definido por el usuario puede [sobrecargar](../keywords/operator.md) los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="4a5be-132">A user-defined type can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="4a5be-133">Si un tipo sobrecarga uno de los dos operadores, también debe sobrecargar el otro.</span><span class="sxs-lookup"><span data-stu-id="4a5be-133">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4a5be-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4a5be-134">C# language specification</span></span>

<span data-ttu-id="4a5be-135">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4a5be-135">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4a5be-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a5be-136">See also</span></span>

- [<span data-ttu-id="4a5be-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4a5be-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4a5be-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4a5be-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4a5be-139">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4a5be-139">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="4a5be-140">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="4a5be-140">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
- [<span data-ttu-id="4a5be-141">Operadores de comparación</span><span class="sxs-lookup"><span data-stu-id="4a5be-141">Comparison operators</span></span>](comparison-operators.md)
