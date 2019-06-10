---
title: 'Operador (): Referencia de C#'
ms.custom: seodec18
ms.date: 01/15/2019
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 8f7382a49c81b6fd8e104b864ffc2f70db7fe4a6
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758113"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9de26-102">Operador () (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9de26-102">() operator (C# Reference)</span></span>

<span data-ttu-id="9de26-103">Los paréntesis, `()`, se suelen usar para la invocación de método o delegado, o en expresiones Cast.</span><span class="sxs-lookup"><span data-stu-id="9de26-103">Parentheses, `()`, are typically used for method or delegate invocation or in cast expressions.</span></span>

<span data-ttu-id="9de26-104">También usa los paréntesis para especificar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="9de26-104">You also use parentheses to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="9de26-105">Para más información, consulte la sección [Agregar paréntesis](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) del artículo [Operadores](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-105">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="9de26-106">Para ver la lista de operadores ordenados por nivel de precedencia, consulte [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-106">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="method-invocation"></a><span data-ttu-id="9de26-107">Invocación del método.</span><span class="sxs-lookup"><span data-stu-id="9de26-107">Method invocation</span></span>

<span data-ttu-id="9de26-108">En el ejemplo siguiente se muestra cómo invocar un método, con o sin argumentos, y un delegado:</span><span class="sxs-lookup"><span data-stu-id="9de26-108">The following example demonstrates how to invoke a method, with or without arguments, and a delegate:</span></span>

[!code-csharp-interactive[use for invocation](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Invocation)]

<span data-ttu-id="9de26-109">También usa paréntesis al invocar un [constructor](../../programming-guide/classes-and-structs/constructors.md) con un operador [`new`](../keywords/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-109">You also use parentheses when you invoke a [constructor](../../programming-guide/classes-and-structs/constructors.md) with a [`new`](../keywords/new-operator.md) operator.</span></span>

<span data-ttu-id="9de26-110">Para obtener más información sobre los métodos, consulte [Métodos](../../programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-110">For more information about methods, see [Methods](../../programming-guide/classes-and-structs/methods.md).</span></span> <span data-ttu-id="9de26-111">Para obtener más información sobre los delegados, consulte [Delegados](../../programming-guide/delegates/index.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-111">For more information about delegates, see [Delegates](../../programming-guide/delegates/index.md).</span></span>

## <a name="cast-expression"></a><span data-ttu-id="9de26-112">Expresión Cast</span><span class="sxs-lookup"><span data-stu-id="9de26-112">Cast expression</span></span>

<span data-ttu-id="9de26-113">Una expresión Cast con el formato `(T)E` invoca un operador de conversión para convertir el valor de la expresión `E` en el tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="9de26-113">A cast expression of the form `(T)E` invokes a conversion operator to convert the value of expression `E` to type `T`.</span></span> <span data-ttu-id="9de26-114">Si no existe ninguna conversión explícita del tipo de `E` al tipo `T`, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="9de26-114">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="9de26-115">Para obtener información sobre cómo definir un operador de conversión, consulte los artículos sobre las palabras clave [explicit](../keywords/explicit.md) e [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-115">For information about how to define a conversion operator, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

<span data-ttu-id="9de26-116">En el siguiente ejemplo se muestra la conversión de tipos entre los tipos numéricos:</span><span class="sxs-lookup"><span data-stu-id="9de26-116">The following example demonstrates type conversion between numeric types:</span></span>

[!code-csharp-interactive[use for cast](~/samples/csharp/language-reference/operators/InvocationOperatorExamples.cs#Cast)]

<span data-ttu-id="9de26-117">Para obtener más información sobre las conversiones explícitas predefinidas entre tipos numéricos, consulte [Tabla de conversiones numéricas explícitas](../keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-117">For more information about predefined explicit conversions between numeric types, see [Explicit numeric conversions table](../keywords/explicit-numeric-conversions-table.md).</span></span>

<span data-ttu-id="9de26-118">Para obtener más información, consulte [Conversiones de tipos](../../programming-guide/types/casting-and-type-conversions.md) y [Operadores de conversión](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-118">For more information, see [Casting and type conversions](../../programming-guide/types/casting-and-type-conversions.md) and [Conversion operators](../../programming-guide/statements-expressions-operators/conversion-operators.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="9de26-119">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="9de26-119">Operator overloadability</span></span>

<span data-ttu-id="9de26-120">El operador `()` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="9de26-120">The operator `()` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9de26-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9de26-121">C# language specification</span></span>

<span data-ttu-id="9de26-122">Para más información, consulte las secciones [Expresiones de invocación](~/_csharplang/spec/expressions.md#invocation-expressions) y [Expresiones Cast](~/_csharplang/spec/expressions.md#cast-expressions) de la [especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="9de26-122">For more information, see the [Invocation expressions](~/_csharplang/spec/expressions.md#invocation-expressions) and [Cast expressions](~/_csharplang/spec/expressions.md#cast-expressions) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9de26-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de26-123">See also</span></span>

- [<span data-ttu-id="9de26-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9de26-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9de26-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9de26-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9de26-126">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9de26-126">C# Operators</span></span>](index.md)
