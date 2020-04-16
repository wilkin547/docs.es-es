---
title: 'Operadores de prueba de tipos y expresión de conversión: referencia de C#'
description: Obtenga información sobre los operadores de C# que puede usar para comprobar el tipo de resultado de la expresión y convertirla en otro tipo, si es necesario.
ms.date: 06/21/2019
author: pkulikov
f1_keywords:
- is_CSharpKeyword
- as_CSharpKeyword
- ()_CSharpKeyword
- typeof_CSharpKeyword
helpviewer_keywords:
- type-testing operators [C#]
- conversion operators [C#]
- type conversion [C#]
- is operator [C#]
- as operator [C#]
- cast operator [C#]
- cast expression [C#]
- () operator [C#]
- typeof operator [C#]
ms.openlocfilehash: 5a4f1d4c0c2ddd0d3967e15090d8f8c1ac42f83e
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121414"
---
# <a name="type-testing-operators-and-cast-expression-c-reference"></a><span data-ttu-id="5f2d4-103">Operadores de prueba de tipos y expresión de conversión (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5f2d4-103">Type-testing operators and cast expression (C# reference)</span></span>

<span data-ttu-id="5f2d4-104">Puede usar los siguientes operadores y expresiones para realizar la comprobación de tipos o la conversión de tipos:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-104">You can use the following operators and expressions to perform type checking or type conversion:</span></span>

- <span data-ttu-id="5f2d4-105">[operador is](#is-operator): para comprobar si el tipo en tiempo de ejecución de una expresión es compatible con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-105">[is operator](#is-operator): to check if the runtime type of an expression is compatible with a given type</span></span>
- <span data-ttu-id="5f2d4-106">[operador as](#as-operator): para convertir explícitamente una expresión a un tipo determinado si su tipo en tiempo de ejecución es compatible con ese tipo.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-106">[as operator](#as-operator): to explicitly convert an expression to a given type if its runtime type is compatible with that type</span></span>
- <span data-ttu-id="5f2d4-107">[expresión Cast](#cast-expression): para realizar una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-107">[cast expression](#cast-expression): to perform an explicit conversion</span></span>
- <span data-ttu-id="5f2d4-108">[operador typeof](#typeof-operator): para obtener la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-108">[typeof operator](#typeof-operator): to obtain the <xref:System.Type?displayProperty=nameWithType> instance for a type</span></span>

## <a name="is-operator"></a><span data-ttu-id="5f2d4-109">Operador is</span><span class="sxs-lookup"><span data-stu-id="5f2d4-109">is operator</span></span>

<span data-ttu-id="5f2d4-110">El operador `is` comprueba si el tipo en tiempo de ejecución del resultado de una expresión es compatible con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-110">The `is` operator checks if the runtime type of an expression result is compatible with a given type.</span></span> <span data-ttu-id="5f2d4-111">A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-111">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span>

<span data-ttu-id="5f2d4-112">La expresión con el operador `is` de prueba de tipos tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-112">The expression with the type-testing `is` operator has the following form</span></span>

```csharp
E is T
```

<span data-ttu-id="5f2d4-113">donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-113">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter.</span></span> <span data-ttu-id="5f2d4-114">`E` no puede ser un método anónimo ni una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-114">`E` cannot be an anonymous method or a lambda expression.</span></span>

<span data-ttu-id="5f2d4-115">La expresión `E is T` devuelve `true` si el resultado de `E` es distinto de NULL y se puede convertir al tipo `T` por una conversión de referencia, una conversión boxing o una conversión unboxing; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-115">The `E is T` expression returns `true` if the result of `E` is non-null and can be converted to type `T` by a reference conversion, a boxing conversion, or an unboxing conversion; otherwise, it returns `false`.</span></span> <span data-ttu-id="5f2d4-116">El operador `is` no toma en consideración las conversiones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-116">The `is` operator doesn't consider user-defined conversions.</span></span>

<span data-ttu-id="5f2d4-117">En el ejemplo siguiente se muestra que el operador `is` devuelve `true` si el tipo en tiempo de ejecución del resultado de una expresión se deriva de un tipo determinado, es decir, existe una conversión de referencia entre tipos:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-117">The following example demonstrates that the `is` operator returns `true` if the runtime type of an expression result derives from a given type, that is, there exists a reference conversion between types:</span></span>

[!code-csharp[is with reference conversion](snippets/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

<span data-ttu-id="5f2d4-118">En el ejemplo siguiente se muestra que el operador `is` tiene en cuenta las conversiones boxing y unboxing pero no considera las [conversiones numéricas](../builtin-types/numeric-conversions.md):</span><span class="sxs-lookup"><span data-stu-id="5f2d4-118">The next example shows that the `is` operator takes into account boxing and unboxing conversions but doesn't consider [numeric conversions](../builtin-types/numeric-conversions.md):</span></span>

[!code-csharp-interactive[is with int](snippets/TypeTestingAndConversionOperators.cs#IsWithInt)]

<span data-ttu-id="5f2d4-119">Para obtener información acerca de las conversiones de C#, vea el capítulo [Conversiones](~/_csharplang/spec/conversions.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-119">For information about C# conversions, see the [Conversions](~/_csharplang/spec/conversions.md) chapter of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

### <a name="type-testing-with-pattern-matching"></a><span data-ttu-id="5f2d4-120">Prueba de tipos con coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="5f2d4-120">Type testing with pattern matching</span></span>

<span data-ttu-id="5f2d4-121">A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-121">Beginning with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span> <span data-ttu-id="5f2d4-122">En concreto, admite el patrón de tipo de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-122">In particular, it supports the type pattern in the following form:</span></span>

```csharp
E is T v
```

<span data-ttu-id="5f2d4-123">donde `E` es una expresión que devuelve un valor, `T` es el nombre de un tipo o un parámetro de tipo y `v` es una nueva variable local de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-123">where `E` is an expression that returns a value, `T` is the name of a type or a type parameter, and `v` is a new local variable of type `T`.</span></span> <span data-ttu-id="5f2d4-124">Si el resultado de `E` no es NULL y puede convertirse en `T` mediante una conversión de referencia, boxing o unboxing, la expresión `E is T v` devuelve `true` y el valor convertido del resultado de `E` se asigna a la variable `v`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-124">If the result of `E` is non-null and can be converted to `T` by a reference, boxing, or unboxing conversion, the `E is T v` expression returns `true` and the converted value of the result of `E` is assigned to variable `v`.</span></span>

<span data-ttu-id="5f2d4-125">En el siguiente ejemplo se muestra el uso del operador `is` con un patrón de tipo:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-125">The following example demonstrates the usage of the `is` operator with the type pattern:</span></span>

[!code-csharp-interactive[is with type pattern](snippets/TypeTestingAndConversionOperators.cs#IsTypePattern)]

<span data-ttu-id="5f2d4-126">Para obtener más información sobre el patrón de tipo y otros patrones admitidos, consulte [Coincidencia de patrones con is](../keywords/is.md#pattern-matching-with-is).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-126">For more information about the type pattern and other supported patterns, see [Pattern matching with is](../keywords/is.md#pattern-matching-with-is).</span></span>

## <a name="as-operator"></a><span data-ttu-id="5f2d4-127">Operador as</span><span class="sxs-lookup"><span data-stu-id="5f2d4-127">as operator</span></span>

<span data-ttu-id="5f2d4-128">El operador `as` convierte explícitamente el resultado de una expresión en una referencia determinada o un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-128">The `as` operator explicitly converts the result of an expression to a given reference or nullable value type.</span></span> <span data-ttu-id="5f2d4-129">Si la conversión no es posible, el operador `as` devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-129">If the conversion is not possible, the `as` operator returns `null`.</span></span> <span data-ttu-id="5f2d4-130">A diferencia de la [expresión Cast](#cast-expression), el operador `as` no genera nunca una excepción.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-130">Unlike a [cast expression](#cast-expression), the `as` operator never throws an exception.</span></span>

<span data-ttu-id="5f2d4-131">La expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="5f2d4-131">The expression of the form</span></span>

```csharp
E as T
```

<span data-ttu-id="5f2d4-132">donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo produce el mismo resultado que</span><span class="sxs-lookup"><span data-stu-id="5f2d4-132">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter, produces the same result as</span></span>

```csharp
E is T ? (T)(E) : (T)null
```

<span data-ttu-id="5f2d4-133">salvo que `E` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-133">except that `E` is only evaluated once.</span></span>

<span data-ttu-id="5f2d4-134">El operador `as` solo considera las conversiones de referencia, las que aceptan valores NULL, boxing y unboxing.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-134">The `as` operator considers only reference, nullable, boxing, and unboxing conversions.</span></span> <span data-ttu-id="5f2d4-135">No puede usar el operador `as` para realizar una conversión definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-135">You cannot use the `as` operator to perform a user-defined conversion.</span></span> <span data-ttu-id="5f2d4-136">Para ello, use una [expresión Cast](#cast-expression).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-136">To do that, use a [cast expression](#cast-expression).</span></span>

<span data-ttu-id="5f2d4-137">En el siguiente ejemplo se muestra el uso del operador `as`:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-137">The following example demonstrates the usage of the `as` operator:</span></span>

[!code-csharp-interactive[as operator](snippets/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> <span data-ttu-id="5f2d4-138">Como se muestra en el ejemplo anterior, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-138">As the preceding example shows, you need to compare the result of the `as` expression with `null` to check if the conversion is successful.</span></span> <span data-ttu-id="5f2d4-139">A partir de C# 7.0, puede usar el [operador is](#type-testing-with-pattern-matching) para probar si la conversión es correcta y, si es así, asignar su resultado a una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-139">Beginning with C# 7.0, you can use the [is operator](#type-testing-with-pattern-matching) both to test if the conversion succeeds and, if it succeeds, assign its result to a new variable.</span></span>

## <a name="cast-expression"></a><span data-ttu-id="5f2d4-140">Expresión Cast</span><span class="sxs-lookup"><span data-stu-id="5f2d4-140">Cast expression</span></span>

<span data-ttu-id="5f2d4-141">Una expresión de conversión con el formato `(T)E` realiza una conversión explícita del resultado de la expresión `E` al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-141">A cast expression of the form `(T)E` performs an explicit conversion of the result of expression `E` to type `T`.</span></span> <span data-ttu-id="5f2d4-142">Si no existe ninguna conversión explícita del tipo de `E` al tipo `T`, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-142">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="5f2d4-143">En el tiempo de ejecución, una conversión explícita podría no completarse correctamente y una expresión de conversión podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-143">At run time, an explicit conversion might not succeed and a cast expression might throw an exception.</span></span>

<span data-ttu-id="5f2d4-144">El ejemplo siguiente muestra las conversiones explícitas numérica y de referencia:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-144">The following example demonstrates explicit numeric and reference conversions:</span></span>

[!code-csharp-interactive[cast expression](snippets/TypeTestingAndConversionOperators.cs#Cast)]

<span data-ttu-id="5f2d4-145">Para obtener más información sobre las conversiones explícitas, vea la sección [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-145">For information about supported explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="5f2d4-146">Para obtener información sobre cómo definir una conversión personalizada de tipo explícito o implícito, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-146">For information about how to define a custom explicit or implicit type conversion, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="5f2d4-147">Otros usos de ()</span><span class="sxs-lookup"><span data-stu-id="5f2d4-147">Other usages of ()</span></span>

<span data-ttu-id="5f2d4-148">También puede utilizar paréntesis para [llamar a un método o invocar un delegado](member-access-operators.md#invocation-expression-).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-148">You also use parentheses to [call a method or invoke a delegate](member-access-operators.md#invocation-expression-).</span></span>

<span data-ttu-id="5f2d4-149">Sirven además para ajustar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-149">Other use of parentheses is to adjust the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="5f2d4-150">Para obtener más información, vea [Operadores de C# (referencia de C#)](index.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-150">For more information, see [C# operators](index.md).</span></span>

## <a name="typeof-operator"></a><span data-ttu-id="5f2d4-151">typeof (operador)</span><span class="sxs-lookup"><span data-stu-id="5f2d4-151">typeof operator</span></span>

<span data-ttu-id="5f2d4-152">El operador `typeof` obtiene la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-152">The `typeof` operator obtains the <xref:System.Type?displayProperty=nameWithType> instance for a type.</span></span> <span data-ttu-id="5f2d4-153">El argumento del operador `typeof` debe ser el nombre de un tipo o un parámetro de tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-153">The argument to the `typeof` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[typeof operator](snippets/TypeTestingAndConversionOperators.cs#TypeOf)]

<span data-ttu-id="5f2d4-154">También puede usar el operador `typeof` con tipos genéricos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-154">You also can use the `typeof` operator with unbound generic types.</span></span> <span data-ttu-id="5f2d4-155">El nombre de un tipo genérico sin enlazar debe contener el número apropiado de comas, que es inferior en una unidad al número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-155">The name of an unbound generic type must contain the appropriate number of commas, which is one less than the number of type parameters.</span></span> <span data-ttu-id="5f2d4-156">En el siguiente ejemplo se muestra el uso del operador `typeof` con un tipo genérico sin enlazar:</span><span class="sxs-lookup"><span data-stu-id="5f2d4-156">The following example shows the usage of the `typeof` operator with an unbound generic type:</span></span>

[!code-csharp-interactive[typeof unbound generic](snippets/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

<span data-ttu-id="5f2d4-157">Una expresión no puede ser un argumento del operador `typeof`.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-157">An expression cannot be an argument of the `typeof` operator.</span></span> <span data-ttu-id="5f2d4-158">Para obtener la instancia de <xref:System.Type?displayProperty=nameWithType> para el tipo en tiempo de ejecución del resultado de una expresión, use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-158">To get the <xref:System.Type?displayProperty=nameWithType> instance for the runtime type of an expression result, use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method.</span></span>

### <a name="type-testing-with-the-typeof-operator"></a><span data-ttu-id="5f2d4-159">Prueba de tipos con el operador `typeof`</span><span class="sxs-lookup"><span data-stu-id="5f2d4-159">Type testing with the `typeof` operator</span></span>

<span data-ttu-id="5f2d4-160">Use el operador `typeof` para comprobar si el tipo en tiempo de ejecución del resultado de la expresión coincide exactamente con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-160">Use the `typeof` operator to check if the runtime type of the expression result exactly matches a given type.</span></span> <span data-ttu-id="5f2d4-161">En el ejemplo siguiente se muestra la diferencia entre la comprobación de tipos realizada con el operador `typeof` y el [operador is](#is-operator):</span><span class="sxs-lookup"><span data-stu-id="5f2d4-161">The following example demonstrates the difference between type checking performed with the `typeof` operator and the [is operator](#is-operator):</span></span>

[!code-csharp[typeof vs is](snippets/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a><span data-ttu-id="5f2d4-162">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="5f2d4-162">Operator overloadability</span></span>

<span data-ttu-id="5f2d4-163">Los operadores `is`, `as` y `typeof` no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-163">The `is`, `as`, and `typeof` operators cannot be overloaded.</span></span>

<span data-ttu-id="5f2d4-164">Un tipo definido por el usuario no se puede sobrecargar el operador `()`, pero puede definir conversiones de tipos personalizadas que pueden realizarse mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="5f2d4-164">A user-defined type cannot overload the `()` operator, but can define custom type conversions that can be performed by a cast expression.</span></span> <span data-ttu-id="5f2d4-165">Para obtener más información, vea [Operadores de conversión definidos por el usuario](user-defined-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="5f2d4-165">For more information, see [User-defined conversion operators](user-defined-conversion-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5f2d4-166">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5f2d4-166">C# language specification</span></span>

<span data-ttu-id="5f2d4-167">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="5f2d4-167">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="5f2d4-168">El operador is</span><span class="sxs-lookup"><span data-stu-id="5f2d4-168">The is operator</span></span>](~/_csharplang/spec/expressions.md#the-is-operator)
- [<span data-ttu-id="5f2d4-169">El operador as</span><span class="sxs-lookup"><span data-stu-id="5f2d4-169">The as operator</span></span>](~/_csharplang/spec/expressions.md#the-as-operator)
- [<span data-ttu-id="5f2d4-170">Expresiones de conversión</span><span class="sxs-lookup"><span data-stu-id="5f2d4-170">Cast expressions</span></span>](~/_csharplang/spec/expressions.md#cast-expressions)
- [<span data-ttu-id="5f2d4-171">El operador typeof</span><span class="sxs-lookup"><span data-stu-id="5f2d4-171">The typeof operator</span></span>](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a><span data-ttu-id="5f2d4-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f2d4-172">See also</span></span>

- [<span data-ttu-id="5f2d4-173">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5f2d4-173">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5f2d4-174">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="5f2d4-174">C# operators</span></span>](index.md)
- [<span data-ttu-id="5f2d4-175">Procedimiento para convertir de forma segura mediante la coincidencia de patrones y los operadores is y as</span><span class="sxs-lookup"><span data-stu-id="5f2d4-175">How to safely cast by using pattern matching and the is and as operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="5f2d4-176">Elementos genéricos en .NET</span><span class="sxs-lookup"><span data-stu-id="5f2d4-176">Generics in .NET</span></span>](../../../standard/generics/index.md)
