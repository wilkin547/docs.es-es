---
title: 'Operador ==: Referencia de C#'
ms.custom: seodec18
ms.date: 12/14/2018
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: 6d86348eefc87e847267f262141ff49e5d51faae
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655964"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="4fd31-102">Operador == (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="4fd31-102">== Operator (C# Reference)</span></span>

<span data-ttu-id="4fd31-103">El operador de igualdad `==` devuelve `true` si sus operandos son iguales; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-103">The equality operator `==` returns `true` if its operands are equal, `false` otherwise.</span></span>

## <a name="value-types-equality"></a><span data-ttu-id="4fd31-104">Igualdad entre tipos de valor</span><span class="sxs-lookup"><span data-stu-id="4fd31-104">Value types equality</span></span>

<span data-ttu-id="4fd31-105">Los operandos de los [tipos de valor integrados](../keywords/value-types-table.md) son iguales si sus valores son iguales:</span><span class="sxs-lookup"><span data-stu-id="4fd31-105">Operands of the [built-in value types](../keywords/value-types-table.md) are equal if their values are equal:</span></span>

[!code-csharp-interactive[value types equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ValueTypesEquality)]

> [!NOTE]
> <span data-ttu-id="4fd31-106">Para los operadores relacionales `==`, `>`, `<`, `>=` y `<=`, si cualquier operando no es un número (<xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>), el resultado del operador será `false`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-106">For relational operators `==`, `>`, `<`, `>=`, and `<=`, if any of the operands is not a number (<xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType>) the result of operation is `false`.</span></span> <span data-ttu-id="4fd31-107">Esto significa que el valor `NaN` no es mayor, inferior ni igual que cualquier otro valor `double` o `float`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-107">That means that the `NaN` value is neither greater than, less than, nor equal to any other `double` (or `float`) value.</span></span> <span data-ttu-id="4fd31-108">Para obtener más información y ejemplos, vea el artículo de referencia <xref:System.Double.NaN?displayProperty=nameWithType> o <xref:System.Single.NaN?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4fd31-108">For more information and examples, see the <xref:System.Double.NaN?displayProperty=nameWithType> or <xref:System.Single.NaN?displayProperty=nameWithType> reference article.</span></span>

<span data-ttu-id="4fd31-109">Dos operandos del mismo tipo [enum](../keywords/enum.md) son iguales si los valores correspondientes del tipo entero subyacente son iguales.</span><span class="sxs-lookup"><span data-stu-id="4fd31-109">Two operands of the same [enum](../keywords/enum.md) type are equal if the corresponding values of the underlying integral type are equal.</span></span>

<span data-ttu-id="4fd31-110">De forma predeterminada, el operador `==` no está definido por un tipo de [estructura](../keywords/struct.md) definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4fd31-110">By default, the `==` operator is not defined for a user-defined [struct](../keywords/struct.md) type.</span></span> <span data-ttu-id="4fd31-111">Un tipo definido por el usuario puede [sobrecargar](#operator-overloadability) el operador `==`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-111">A user-defined type can [overload](#operator-overloadability) the `==` operator.</span></span>

<span data-ttu-id="4fd31-112">A partir de C# 7,3, los operadores `==` y [`!=`](not-equal-operator.md) son compatibles con las [tuplas](../../tuples.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="4fd31-112">Beginning with C# 7.3, the `==` and [`!=`](not-equal-operator.md) operators are supported by C# [tuples](../../tuples.md).</span></span> <span data-ttu-id="4fd31-113">Para obtener más información, vea la sección [Igualdad y tuplas](../../tuples.md#equality-and-tuples) del artículo [Tipos de tupla de C#](../../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="4fd31-113">For more information, see the [Equality and tuples](../../tuples.md#equality-and-tuples) section of the [C# tuple types](../../tuples.md) article.</span></span>

## <a name="string-equality"></a><span data-ttu-id="4fd31-114">Igualdad entre cadenas</span><span class="sxs-lookup"><span data-stu-id="4fd31-114">String equality</span></span>

<span data-ttu-id="4fd31-115">Dos operandos [string](../keywords/string.md) son iguales si ambos son `null`, o bien si las instancias de ambas cadenas tienen la misma longitud y los mismos caracteres en cada posición de caracteres:</span><span class="sxs-lookup"><span data-stu-id="4fd31-115">Two [string](../keywords/string.md) operands are equal when both of them are `null` or both string instances are of the same length and have identical characters in each character position:</span></span>

[!code-csharp-interactive[string equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#StringEquality)]

<span data-ttu-id="4fd31-116">Es la comparación de ordinales que distingue entre mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4fd31-116">That is case-sensitive ordinal comparison.</span></span> <span data-ttu-id="4fd31-117">Para obtener más información sobre cómo comparar cadenas, vea [Cómo comparar cadenas en C# ](../../how-to/compare-strings.md).</span><span class="sxs-lookup"><span data-stu-id="4fd31-117">For more information about how to compare strings, see [How to compare strings in C#](../../how-to/compare-strings.md).</span></span>

## <a name="reference-types-equality"></a><span data-ttu-id="4fd31-118">Igualdad entre tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="4fd31-118">Reference types equality</span></span>

<span data-ttu-id="4fd31-119">Dos operandos de tipos de referencia (excepto `string`) son iguales si hacen referencia al mismo objeto:</span><span class="sxs-lookup"><span data-stu-id="4fd31-119">Two other than `string` reference type operands are equal when they refer to the same object:</span></span>

[!code-csharp-interactive[reference type equality](~/samples/snippets/csharp/language-reference/operators/EqualityAndNonEqualityExamples.cs#ReferenceTypesEquality)]

<span data-ttu-id="4fd31-120">En el ejemplo se muestra que el operador `==` es compatible con los tipos de referencia definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4fd31-120">The example shows that the `==` operator is supported by user-defined reference types.</span></span> <span data-ttu-id="4fd31-121">Sin embargo, un tipo de referencia definido por el usuario puede sobrecargar el operador `==`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-121">However, a user-defined reference type can overload the `==` operator.</span></span> <span data-ttu-id="4fd31-122">Si un tipo de referencia sobrecarga el operador `==`, use el método <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> para comprobar si dos referencias de ese tipo hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="4fd31-122">If a reference type overloads the `==` operator, use the <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method to check if two references of that type refer to the same object.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="4fd31-123">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="4fd31-123">Operator overloadability</span></span>

<span data-ttu-id="4fd31-124">Los tipos definidos por el usuario pueden [sobrecargar](../keywords/operator.md) el operador `==`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-124">User-defined types can [overload](../keywords/operator.md) the `==` operator.</span></span> <span data-ttu-id="4fd31-125">Si un tipo sobrecarga el operador de igualdad `==`, también debe sobrecargar el [operador de desigualdad](not-equal-operator.md) `!=`.</span><span class="sxs-lookup"><span data-stu-id="4fd31-125">If a type overloads the equality operator `==`, it must also overload the [inequality operator](not-equal-operator.md) `!=`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4fd31-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="4fd31-126">C# language specification</span></span>

<span data-ttu-id="4fd31-127">Para obtener más información, vea la sección [Operadores de comprobación de tipos y relacionales](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) de la [Especificación del lenguaje de C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="4fd31-127">For more information, see the [Relational and type-testing operators](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4fd31-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fd31-128">See also</span></span>

- [<span data-ttu-id="4fd31-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="4fd31-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4fd31-130">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4fd31-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4fd31-131">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="4fd31-131">C# Operators</span></span>](index.md)
- [<span data-ttu-id="4fd31-132">Comparaciones de igualdad</span><span class="sxs-lookup"><span data-stu-id="4fd31-132">Equality comparisons</span></span>](../../programming-guide/statements-expressions-operators/equality-comparisons.md)
