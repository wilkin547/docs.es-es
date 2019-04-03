---
title: 'Operadores de igualdad: referencia de C#'
ms.date: 03/28/2019
author: pkulikov
f1_keywords:
- ==_CSharpKeyword
- '!=_CSharpKeyword'
helpviewer_keywords:
- equality operator [C#]
- equals operator [C#]
- == operator [C#]
- inequality operator [C#]
- not equals operator [C#]
- '!= operator [C#]'
ms.openlocfilehash: 98b96f5b4c6d6ea70687a97c849e89573c67c37e
ms.sourcegitcommit: 4a8c2b8d0df44142728b68ebc842575840476f6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545900"
---
# <a name="equality-operators-c-reference"></a><span data-ttu-id="6cb16-102">Operadores de igualdad (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6cb16-102">Equality operators (C# Reference)</span></span>

<span data-ttu-id="6cb16-103">Los operadores [`==` (igualdad)](#equality-operator-) y [`!=` (desigualdad)](#inequality-operator-) comprueban si los operandos son iguales.</span><span class="sxs-lookup"><span data-stu-id="6cb16-103">The [`==` (equality)](#equality-operator-) and [`!=` (inequality)](#inequality-operator-) operators check if their operands are equal or not.</span></span>

## <a name="equality-operator-"></a><span data-ttu-id="6cb16-104">Operador de igualdad ==</span><span class="sxs-lookup"><span data-stu-id="6cb16-104">Equality operator ==</span></span>

<span data-ttu-id="6cb16-105">El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-105">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

### <a name="value-types-equality"></a><span data-ttu-id="6cb16-106">Igualdad entre tipos de valor</span><span class="sxs-lookup"><span data-stu-id="6cb16-106">Value types equality</span></span>

<span data-ttu-id="6cb16-107">Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:</span><span class="sxs-lookup"><span data-stu-id="6cb16-107">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="6cb16-108">Para los operadores de igualdad y relacionales `==`, `>`, `<`, `>=` y `<=`, si uno de los operandos no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado de la operación será `false`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-108">For equality and relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>), the result of operation is `false`.</span></span> <span data-ttu-id="6cb16-109">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`, incluido `NaN`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-109">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value, including `NaN`.</span></span> <span data-ttu-id="6cb16-110">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6cb16-110">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="6cb16-111">Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.</span><span class="sxs-lookup"><span data-stu-id="6cb16-111">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="6cb16-112">Los tipos [struct](../keywords/struct.md) definidos por el usuario no son compatibles con el operador `==` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6cb16-112">User-defined [struct](../keywords/struct.md) types don't support the `==` operator by default.</span></span> <span data-ttu-id="6cb16-113">Para admitir el operador `==`, un elemento struct definido por el usuario debe [sobrecargarlo](#operator-overloadability).</span><span class="sxs-lookup"><span data-stu-id="6cb16-113">To support the `==` operator, a user-defined struct must [overload](#operator-overloadability) it.</span></span>

<span data-ttu-id="6cb16-114">A partir de C# 7.3, los operadores `==` y `!=` son compatibles con las [tuplas](../../tuples.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="6cb16-114">Beginning with C# 7.3, the `==` and `!=` operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="6cb16-115">Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="6cb16-115">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

### <a name="string-equality"></a><span data-ttu-id="6cb16-116">Igualdad entre cadenas</span><span class="sxs-lookup"><span data-stu-id="6cb16-116">String equality</span></span>

<span data-ttu-id="6cb16-117">Dos operandos [string](../keywords/string.md) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:</span><span class="sxs-lookup"><span data-stu-id="6cb16-117">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="6cb16-118">Es la comparación de ordinales que distingue entre mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6cb16-118">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="6cb16-119">Para obtener más información sobre la comparación de cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="6cb16-119">For more information about string comparison, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

### <a name="reference-types-equality"></a><span data-ttu-id="6cb16-120">Igualdad entre tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="6cb16-120">Reference types equality</span></span>

<span data-ttu-id="6cb16-121">Dos operandos de tipos de referencia (excepto `string`) son iguales si hacen referencia al mismo objeto:</span><span class="sxs-lookup"><span data-stu-id="6cb16-121">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="6cb16-122">Como se muestra en el ejemplo, el operador `==` es compatible de forma predeterminada con los tipos de referencia definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6cb16-122">As the example shows, user-defined reference types support the `==` operator by default.</span></span> <span data-ttu-id="6cb16-123">Sin embargo, un tipo de referencia definido por el usuario puede sobrecargar el operador `==`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-123">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="6cb16-124">Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="6cb16-124">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="inequality-operator-"></a><span data-ttu-id="6cb16-125">Operador de desigualdad !=</span><span class="sxs-lookup"><span data-stu-id="6cb16-125">Inequality operator !=</span></span>

<span data-ttu-id="6cb16-126">El operador de desigualdad (`!=`) devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-126">The inequality operator `!=` returns `true` if its operands are not equal, `false` otherwise.</span></span> <span data-ttu-id="6cb16-127">Para los operandos de los [tipos integrados](../keywords/built-in-types-table.md), la expresión `x != y` genera el mismo resultado que la expresión `!(x == y)`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-127">For the operands of the [built-in types](../keywords/built-in-types-table.md), the expression `x != y` produces the same result as the expression `!(x == y)`.</span></span> <span data-ttu-id="6cb16-128">Para obtener más información sobre la igualdad de tipos, vea la sección [Operador de igualdad](#equality-operator-).</span><span class="sxs-lookup"><span data-stu-id="6cb16-128">For more information about type equality, see the [Equality operator](#equality-operator-) section.</span></span>

<span data-ttu-id="6cb16-129">En el siguiente ejemplo se muestra el uso del operador `!=`:</span><span class="sxs-lookup"><span data-stu-id="6cb16-129">The following example demonstrates the usage of the `!=` operator:</span></span>

[!code-csharp-interactive[non-equality examples](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#NonEquality)]

## <a name="operator-overloadability"></a><span data-ttu-id="6cb16-130">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="6cb16-130">Operator overloadability</span></span>

<span data-ttu-id="6cb16-131">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) los operadores `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="6cb16-131">User-defined types can [overload](../keywords/operator.md) the `==` and `!=` operators.</span></span> <span data-ttu-id="6cb16-132">Si un tipo sobrecarga uno de los dos operadores, también debe sobrecargar el otro.</span><span class="sxs-lookup"><span data-stu-id="6cb16-132">If a type overloads one of the two operators, it must also overload another one.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6cb16-133">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6cb16-133">C# language specification</span></span>

<span data-ttu-id="6cb16-134">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="6cb16-134">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6cb16-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="6cb16-135">See also</span></span>

- [<span data-ttu-id="6cb16-136">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6cb16-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6cb16-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6cb16-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6cb16-138">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6cb16-138">C# Operators</span></span>](index.md)
- <xref:System.IEquatable%601?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6cb16-139">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="6cb16-139">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
