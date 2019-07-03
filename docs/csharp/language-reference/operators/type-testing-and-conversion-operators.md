---
title: 'Operadores de conversión y prueba de tipos: referencia de C#'
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
ms.openlocfilehash: 4468bc86634ad97f2dfbdb5f842eb5206f957a79
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307516"
---
# <a name="type-testing-and-conversion-operators-c-reference"></a><span data-ttu-id="20cd3-103">Operadores de conversión y prueba de tipos (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="20cd3-103">Type-testing and conversion operators (C# reference)</span></span>

<span data-ttu-id="20cd3-104">Puede usar los siguientes operadores para realizar la comprobación de tipos o la conversión de tipos:</span><span class="sxs-lookup"><span data-stu-id="20cd3-104">You can use the following operators to perform type checking or type conversion:</span></span>

- <span data-ttu-id="20cd3-105">[operador is](#is-operator): para comprobar si el tipo en tiempo de ejecución de una expresión es compatible con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="20cd3-105">[is operator](#is-operator): to check if the runtime type of an expression is compatible with a given type</span></span>
- <span data-ttu-id="20cd3-106">[operador as](#as-operator): para convertir explícitamente una expresión a un tipo determinado si su tipo en tiempo de ejecución es compatible con ese tipo.</span><span class="sxs-lookup"><span data-stu-id="20cd3-106">[as operator](#as-operator): to explicitly convert an expression to a given type if its runtime type is compatible with that type</span></span>
- <span data-ttu-id="20cd3-107">[operador de conversión ()](#cast-operator-): para realizar una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="20cd3-107">[cast operator ()](#cast-operator-): to perform an explicit conversion</span></span>
- <span data-ttu-id="20cd3-108">[operador typeof](#typeof-operator): para obtener la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo.</span><span class="sxs-lookup"><span data-stu-id="20cd3-108">[typeof operator](#typeof-operator): to obtain the <xref:System.Type?displayProperty=nameWithType> instance for a type</span></span>

## <a name="is-operator"></a><span data-ttu-id="20cd3-109">Operador is</span><span class="sxs-lookup"><span data-stu-id="20cd3-109">is operator</span></span>

<span data-ttu-id="20cd3-110">El operador `is` comprueba si el tipo en tiempo de ejecución del resultado de una expresión es compatible con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="20cd3-110">The `is` operator checks if the runtime type of an expression result is compatible with a given type.</span></span> <span data-ttu-id="20cd3-111">A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón.</span><span class="sxs-lookup"><span data-stu-id="20cd3-111">Starting with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span>

<span data-ttu-id="20cd3-112">La expresión con el operador `is` de prueba de tipos tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="20cd3-112">The expression with the type-testing `is` operator has the following form</span></span>

```csharp
E is T
```

<span data-ttu-id="20cd3-113">donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="20cd3-113">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter.</span></span> <span data-ttu-id="20cd3-114">`E` no puede ser un método anónimo ni una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="20cd3-114">`E` cannot be an anonymous method or a lambda expression.</span></span>

<span data-ttu-id="20cd3-115">La expresión `E is T` devuelve `true` si el resultado de `E` es distinto de NULL y se puede convertir al tipo `T` por una conversión de referencia, una conversión boxing o una conversión unboxing; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-115">The `E is T` expression returns `true` if the result of `E` is non-null and can be converted to type `T` by a reference conversion, a boxing conversion, or an unboxing conversion; otherwise, it returns `false`.</span></span> <span data-ttu-id="20cd3-116">El operador `is` no toma en consideración las conversiones definidas por el usuario.</span><span class="sxs-lookup"><span data-stu-id="20cd3-116">The `is` operator doesn't consider user-defined conversions.</span></span>

<span data-ttu-id="20cd3-117">En el ejemplo siguiente se muestra que el operador `is` devuelve `true` si el tipo en tiempo de ejecución del resultado de una expresión se deriva de un tipo determinado, es decir, existe una conversión de referencia entre tipos:</span><span class="sxs-lookup"><span data-stu-id="20cd3-117">The following example demonstrates that the `is` operator returns `true` if the runtime type of an expression result derives from a given type, that is, there exists a reference conversion between types:</span></span>

[!code-csharp[is with reference conversion](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithReferenceConversion)]

<span data-ttu-id="20cd3-118">En el ejemplo siguiente se muestra que el operador `is` tiene en cuenta las conversiones boxing y unboxing pero no considera las conversiones numéricas:</span><span class="sxs-lookup"><span data-stu-id="20cd3-118">The next example shows that the `is` operator takes into account boxing and unboxing conversions but doesn't consider numeric conversions:</span></span>

[!code-csharp-interactive[is with int](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsWithInt)]

<span data-ttu-id="20cd3-119">Para obtener información acerca de las conversiones de C#, vea el capítulo [Conversiones](~/_csharplang/spec/conversions.md) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="20cd3-119">For information about C# conversions, see the [Conversions](~/_csharplang/spec/conversions.md) chapter of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

### <a name="type-testing-with-pattern-matching"></a><span data-ttu-id="20cd3-120">Prueba de tipos con coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="20cd3-120">Type testing with pattern matching</span></span>

<span data-ttu-id="20cd3-121">A partir de C# 7.0, el operador `is` también prueba el resultado de una expresión en relación con un patrón.</span><span class="sxs-lookup"><span data-stu-id="20cd3-121">Starting with C# 7.0, the `is` operator also tests an expression result against a pattern.</span></span> <span data-ttu-id="20cd3-122">En concreto, admite el patrón de tipo de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="20cd3-122">In particular, it supports the type pattern in the following form:</span></span>

```csharp
E is T v
```

<span data-ttu-id="20cd3-123">donde `E` es una expresión que devuelve un valor, `T` es el nombre de un tipo o un parámetro de tipo y `v` es una nueva variable local de tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-123">where `E` is an expression that returns a value, `T` is the name of a type or a type parameter, and `v` is a new local variable of type `T`.</span></span> <span data-ttu-id="20cd3-124">Si el resultado de `E` no es NULL y puede convertirse en `T` mediante una conversión de referencia, boxing o unboxing, la expresión `E is T v` devuelve `true` y el valor convertido del resultado de `E` se asigna a la variable `v`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-124">If the result of `E` is non-null and can be converted to `T` by a reference, boxing, or unboxing conversion, the `E is T v` expression returns `true` and the converted value of the result of `E` is assigned to variable `v`.</span></span>

<span data-ttu-id="20cd3-125">En el siguiente ejemplo se muestra el uso del operador `is` con un patrón de tipo:</span><span class="sxs-lookup"><span data-stu-id="20cd3-125">The following example demonstrates the usage of the `is` operator with the type pattern:</span></span>

[!code-csharp-interactive[is with type pattern](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#IsTypePattern)]

<span data-ttu-id="20cd3-126">Para obtener más información sobre el patrón de tipo y otros patrones admitidos, consulte [Coincidencia de patrones con is](../keywords/is.md#pattern-matching-with-is).</span><span class="sxs-lookup"><span data-stu-id="20cd3-126">For more information about the type pattern and other supported patterns, see [Pattern matching with is](../keywords/is.md#pattern-matching-with-is).</span></span>

## <a name="as-operator"></a><span data-ttu-id="20cd3-127">Operador as</span><span class="sxs-lookup"><span data-stu-id="20cd3-127">as operator</span></span>

<span data-ttu-id="20cd3-128">El operador `as` convierte explícitamente el resultado de una expresión en una referencia determinada o un tipo de valor que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="20cd3-128">The `as` operator explicitly converts the result of an expression to a given reference or nullable value type.</span></span> <span data-ttu-id="20cd3-129">Si la conversión no es posible, el operador `as` devuelve `null`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-129">If the conversion is not possible, the `as` operator returns `null`.</span></span> <span data-ttu-id="20cd3-130">A diferencia del [operador de conversión ()](#cast-operator-), el operador `as` no genera nunca una excepción.</span><span class="sxs-lookup"><span data-stu-id="20cd3-130">Unlike the [cast operator ()](#cast-operator-), the `as` operator never throws an exception.</span></span>

<span data-ttu-id="20cd3-131">La expresión con el formato</span><span class="sxs-lookup"><span data-stu-id="20cd3-131">The expression of the form</span></span>

```csharp
E as T
```

<span data-ttu-id="20cd3-132">donde `E` es una expresión que devuelve un valor y `T` es el nombre de un tipo o un parámetro de tipo produce el mismo resultado que</span><span class="sxs-lookup"><span data-stu-id="20cd3-132">where `E` is an expression that returns a value and `T` is the name of a type or a type parameter, produces the same result as</span></span>

```csharp
E is T ? (T)(E) : (T)null
```

<span data-ttu-id="20cd3-133">salvo que `E` solo se evalúa una vez.</span><span class="sxs-lookup"><span data-stu-id="20cd3-133">except that `E` is only evaluated once.</span></span>

<span data-ttu-id="20cd3-134">El operador `as` solo considera las conversiones de referencia, las que aceptan valores NULL, boxing y unboxing.</span><span class="sxs-lookup"><span data-stu-id="20cd3-134">The `as` operator considers only reference, nullable, boxing, and unboxing conversions.</span></span> <span data-ttu-id="20cd3-135">No puede usar el operador `as` para realizar una conversión definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="20cd3-135">You cannot use the `as` operator to perform a user-defined conversion.</span></span> <span data-ttu-id="20cd3-136">Para hacerlo, utilice el [operador de conversión ()](#cast-operator-).</span><span class="sxs-lookup"><span data-stu-id="20cd3-136">To do that, use the [cast operator ()](#cast-operator-).</span></span>

<span data-ttu-id="20cd3-137">En el siguiente ejemplo se muestra el uso del operador `as`:</span><span class="sxs-lookup"><span data-stu-id="20cd3-137">The following example demonstrates the usage of the `as` operator:</span></span>

[!code-csharp-interactive[as operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#AsOperator)]

> [!NOTE]
> <span data-ttu-id="20cd3-138">Como se muestra en el ejemplo anterior, se necesita comparar el resultado de la expresión `as` con `null` para comprobar si una conversión es correcta.</span><span class="sxs-lookup"><span data-stu-id="20cd3-138">As the preceding example shows, you need to compare the result of the `as` expression with `null` to check if the conversion is successful.</span></span> <span data-ttu-id="20cd3-139">A partir de C# 7.0, puede usar el [operador is](#type-testing-with-pattern-matching) para probar si la conversión es correcta y, si es así, asignar su resultado a una nueva variable.</span><span class="sxs-lookup"><span data-stu-id="20cd3-139">Starting with C# 7.0, you can use the [is operator](#type-testing-with-pattern-matching) both to test if the conversion succeeds and, if it succeeds, assign its result to a new variable.</span></span>

## <a name="cast-operator-"></a><span data-ttu-id="20cd3-140">Operador de conversión ()</span><span class="sxs-lookup"><span data-stu-id="20cd3-140">Cast operator ()</span></span>

<span data-ttu-id="20cd3-141">Una expresión de conversión con el formato `(T)E` realiza una conversión explícita del resultado de la expresión `E` al tipo `T`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-141">A cast expression of the form `(T)E` performs an explicit conversion of the result of expression `E` to type `T`.</span></span> <span data-ttu-id="20cd3-142">Si no existe ninguna conversión explícita del tipo de `E` al tipo `T`, se producirá un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="20cd3-142">If no explicit conversion exists from the type of `E` to type `T`, a compile-time error occurs.</span></span> <span data-ttu-id="20cd3-143">En el tiempo de ejecución, una conversión explícita podría no completarse correctamente y una expresión de conversión podría generar una excepción.</span><span class="sxs-lookup"><span data-stu-id="20cd3-143">At run time, an explicit conversion might not succeed and a cast expression might throw an exception.</span></span>

<span data-ttu-id="20cd3-144">El ejemplo siguiente muestra las conversiones explícitas numérica y de referencia:</span><span class="sxs-lookup"><span data-stu-id="20cd3-144">The following example demonstrates explicit numeric and reference conversions:</span></span>

[!code-csharp-interactive[cast expression](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#Cast)]

<span data-ttu-id="20cd3-145">Para obtener más información sobre las conversiones explícitas, vea la sección [Conversiones explícitas](~/_csharplang/spec/conversions.md#explicit-conversions) de la [especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="20cd3-145">For information about supported explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span> <span data-ttu-id="20cd3-146">Para obtener información sobre cómo definir una conversión personalizada de tipo explícito o implícito, consulte el artículo con la palabra clave [explicit](../keywords/explicit.md) o [implicit](../keywords/implicit.md), respectivamente.</span><span class="sxs-lookup"><span data-stu-id="20cd3-146">For information about how to define a custom explicit or implicit type conversion, see the [explicit](../keywords/explicit.md) or [implicit](../keywords/implicit.md) keyword article, respectively.</span></span>

### <a name="other-usages-of-"></a><span data-ttu-id="20cd3-147">Otros usos de ()</span><span class="sxs-lookup"><span data-stu-id="20cd3-147">Other usages of ()</span></span>

<span data-ttu-id="20cd3-148">También puede utilizar paréntesis para [llamar a un método o invocar un delegado](member-access-operators.md#invocation-operator-).</span><span class="sxs-lookup"><span data-stu-id="20cd3-148">You also use parentheses to [call a method or invoke a delegate](member-access-operators.md#invocation-operator-).</span></span>

<span data-ttu-id="20cd3-149">Sirven además para especificar el orden en el que se van a evaluar operaciones en una expresión.</span><span class="sxs-lookup"><span data-stu-id="20cd3-149">Other use of parentheses is to specify the order in which to evaluate operations in an expression.</span></span> <span data-ttu-id="20cd3-150">Para más información, consulte la sección [Agregar paréntesis](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) del artículo [Operadores](../../programming-guide/statements-expressions-operators/operators.md).</span><span class="sxs-lookup"><span data-stu-id="20cd3-150">For more information, see the [Adding parentheses](../../programming-guide/statements-expressions-operators/operators.md#adding-parentheses) section of the [Operators](../../programming-guide/statements-expressions-operators/operators.md) article.</span></span> <span data-ttu-id="20cd3-151">Para ver la lista de operadores ordenados por nivel de precedencia, consulte [Operadores de C#](index.md).</span><span class="sxs-lookup"><span data-stu-id="20cd3-151">For the list of operators ordered by precedence level, see [C# operators](index.md).</span></span>

## <a name="typeof-operator"></a><span data-ttu-id="20cd3-152">Operador typeof</span><span class="sxs-lookup"><span data-stu-id="20cd3-152">typeof operator</span></span>

<span data-ttu-id="20cd3-153">El operador `typeof` obtiene la instancia <xref:System.Type?displayProperty=nameWithType> para un tipo.</span><span class="sxs-lookup"><span data-stu-id="20cd3-153">The `typeof` operator obtains the <xref:System.Type?displayProperty=nameWithType> instance for a type.</span></span> <span data-ttu-id="20cd3-154">Un argumento del operador `typeof` debe ser el nombre de un tipo o un parámetro de tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="20cd3-154">An argument of the `typeof` operator must be the name of a type or a type parameter, as the following example shows:</span></span>

[!code-csharp-interactive[typeof operator](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOf)]

<span data-ttu-id="20cd3-155">También puede usar el operador `typeof` con tipos genéricos sin enlazar.</span><span class="sxs-lookup"><span data-stu-id="20cd3-155">You also can use the `typeof` operator with unbound generic types.</span></span> <span data-ttu-id="20cd3-156">El nombre de un tipo genérico sin enlazar debe contener el número apropiado de comas, que es inferior en una unidad al número de parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="20cd3-156">The name of an unbound generic type must contain the appropriate number of commas, which is one less than the number of type parameters.</span></span> <span data-ttu-id="20cd3-157">En el siguiente ejemplo se muestra el uso del operador `typeof` con un tipo genérico sin enlazar:</span><span class="sxs-lookup"><span data-stu-id="20cd3-157">The following example shows the usage of the `typeof` operator with an unbound generic type:</span></span>

[!code-csharp-interactive[typeof unbound generic](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeOfUnboundGeneric)]

<span data-ttu-id="20cd3-158">Una expresión no puede ser un argumento del operador `typeof`.</span><span class="sxs-lookup"><span data-stu-id="20cd3-158">An expression cannot be an argument of the `typeof` operator.</span></span> <span data-ttu-id="20cd3-159">Para obtener la instancia <xref:System.Type?displayProperty=nameWithType> para el tipo en tiempo de ejecución del resultado de la expresión, use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="20cd3-159">To get the <xref:System.Type?displayProperty=nameWithType> instance for the runtime type of the expression result, use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method.</span></span>

### <a name="type-testing-with-the-typeof-operator"></a><span data-ttu-id="20cd3-160">Prueba de tipos con el operador `typeof`</span><span class="sxs-lookup"><span data-stu-id="20cd3-160">Type testing with the `typeof` operator</span></span>

<span data-ttu-id="20cd3-161">Use el operador `typeof` para comprobar si el tipo en tiempo de ejecución del resultado de la expresión coincide exactamente con un tipo determinado.</span><span class="sxs-lookup"><span data-stu-id="20cd3-161">Use the `typeof` operator to check if the runtime type of the expression result exactly matches a given type.</span></span> <span data-ttu-id="20cd3-162">En el ejemplo siguiente se muestra la diferencia entre la comprobación de tipos realizada con el operador `typeof` y el [operador is](#is-operator):</span><span class="sxs-lookup"><span data-stu-id="20cd3-162">The following example demonstrates the difference between type checking performed with the `typeof` operator and the [is operator](#is-operator):</span></span>

[!code-csharp[typeof vs is](~/samples/csharp/language-reference/operators/TypeTestingAndConversionOperators.cs#TypeCheckWithTypeOf)]

## <a name="operator-overloadability"></a><span data-ttu-id="20cd3-163">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="20cd3-163">Operator overloadability</span></span>

<span data-ttu-id="20cd3-164">Los operadores `is`, `as` y `typeof` no son sobrecargables.</span><span class="sxs-lookup"><span data-stu-id="20cd3-164">The `is`, `as`, and `typeof` operators are not overloadable.</span></span>

<span data-ttu-id="20cd3-165">Un tipo definido por el usuario no se puede sobrecargar el operador `()`, pero puede definir conversiones de tipos personalizadas que pueden realizarse mediante una expresión de conversión.</span><span class="sxs-lookup"><span data-stu-id="20cd3-165">A user-defined type cannot overload the `()` operator, but can define custom type conversions that can be performed by a cast expression.</span></span> <span data-ttu-id="20cd3-166">Para más información, consulte los artículos sobre las palabras clave [explicit](../keywords/explicit.md) e [implicit](../keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="20cd3-166">For more information, see the [explicit](../keywords/explicit.md) and [implicit](../keywords/implicit.md) keyword articles.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="20cd3-167">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="20cd3-167">C# language specification</span></span>

<span data-ttu-id="20cd3-168">Para más información, vea las secciones siguientes de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md):</span><span class="sxs-lookup"><span data-stu-id="20cd3-168">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="20cd3-169">El operador is</span><span class="sxs-lookup"><span data-stu-id="20cd3-169">The is operator</span></span>](~/_csharplang/spec/expressions.md#the-is-operator)
- [<span data-ttu-id="20cd3-170">El operador as</span><span class="sxs-lookup"><span data-stu-id="20cd3-170">The as operator</span></span>](~/_csharplang/spec/expressions.md#the-as-operator)
- [<span data-ttu-id="20cd3-171">Expresiones de conversión</span><span class="sxs-lookup"><span data-stu-id="20cd3-171">Cast expressions</span></span>](~/_csharplang/spec/expressions.md#cast-expressions)
- [<span data-ttu-id="20cd3-172">El operador typeof</span><span class="sxs-lookup"><span data-stu-id="20cd3-172">The typeof operator</span></span>](~/_csharplang/spec/expressions.md#the-typeof-operator)

## <a name="see-also"></a><span data-ttu-id="20cd3-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="20cd3-173">See also</span></span>

- [<span data-ttu-id="20cd3-174">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="20cd3-174">C# reference</span></span>](../index.md)
- [<span data-ttu-id="20cd3-175">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="20cd3-175">C# operators</span></span>](index.md)
- [<span data-ttu-id="20cd3-176">Cómo: Convertir de forma segura mediante la coincidencia de patrones y los operadores is y as</span><span class="sxs-lookup"><span data-stu-id="20cd3-176">How to: safely cast by using pattern matching and the is and as operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
