---
title: 'is: Referencia de C#'
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 1a1f539e80f8d843f40640fa798cf6122f316a9f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715233"
---
# <a name="is-c-reference"></a><span data-ttu-id="3df53-102">is (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3df53-102">is (C# Reference)</span></span>

<span data-ttu-id="3df53-103">El operador `is` comprueba si el resultado de una expresión es compatible con un tipo determinado o, a partir de C# 7.0, prueba una expresión en un patrón.</span><span class="sxs-lookup"><span data-stu-id="3df53-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="3df53-104">Para obtener información sobre el operador de prueba de tipos `is`, consulte la sección [operador is](../operators/type-testing-and-cast.md#is-operator) del artículo [Operadores de conversión y prueba de tipos](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="3df53-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="3df53-105">Coincidencia de patrones con `is`</span><span class="sxs-lookup"><span data-stu-id="3df53-105">Pattern matching with `is`</span></span>

<span data-ttu-id="3df53-106">A partir de C# 7.0, las instrucciones `is` y [switch](switch.md) admiten la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="3df53-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="3df53-107">La palabra clave `is` admite los patrones siguientes:</span><span class="sxs-lookup"><span data-stu-id="3df53-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="3df53-108">[Patrón de tipo](#type-pattern), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3df53-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="3df53-109">[Patrón de constante](#constant-pattern), que comprueba si una expresión se evalúa como un valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="3df53-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="3df53-110">[Patrón var](#var-pattern), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.</span><span class="sxs-lookup"><span data-stu-id="3df53-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="3df53-111">Patrón de tipo</span><span class="sxs-lookup"><span data-stu-id="3df53-111">Type pattern</span></span>

<span data-ttu-id="3df53-112">Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3df53-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="3df53-113">Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa.</span><span class="sxs-lookup"><span data-stu-id="3df53-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="3df53-114">La forma general del patrón de tipos `is` es:</span><span class="sxs-lookup"><span data-stu-id="3df53-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="3df53-115">donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.</span><span class="sxs-lookup"><span data-stu-id="3df53-115">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="3df53-116">La expresión `is` es `true` si *expr* no es `null` y se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="3df53-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="3df53-117">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="3df53-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="3df53-118">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="3df53-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="3df53-119">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="3df53-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="3df53-120">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="3df53-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="3df53-121">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="3df53-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="3df53-122">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="3df53-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="3df53-123">*type* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="3df53-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="3df53-124">A partir de C# 7.1, *expr* puede tener un tipo de tiempo de compilación definido por un parámetro y sus restricciones.</span><span class="sxs-lookup"><span data-stu-id="3df53-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="3df53-125">Si *expr* es `true` y `is` se usa con una instrucción `if`, solo se asigna *varname* dentro de la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="3df53-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="3df53-126">El ámbito de *varname* abarca de la expresión `is` al final del bloque que incluye la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="3df53-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="3df53-127">El uso de *varname* en cualquier otra ubicación genera un error en tiempo de compilación por el uso de una variable que no se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="3df53-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="3df53-128">En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de tipo.</span><span class="sxs-lookup"><span data-stu-id="3df53-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="3df53-129">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3df53-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="3df53-130">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.</span><span class="sxs-lookup"><span data-stu-id="3df53-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="3df53-131">El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="3df53-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="3df53-132">En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.</span><span class="sxs-lookup"><span data-stu-id="3df53-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="3df53-133">El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="3df53-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="3df53-134">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="3df53-134">Constant pattern</span></span>

<span data-ttu-id="3df53-135">Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="3df53-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="3df53-136">En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="3df53-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="3df53-137">A partir de C# 7.0, la instrucción `is` también lo admite.</span><span class="sxs-lookup"><span data-stu-id="3df53-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="3df53-138">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="3df53-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="3df53-139">donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="3df53-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="3df53-140">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="3df53-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="3df53-141">Un valor literal.</span><span class="sxs-lookup"><span data-stu-id="3df53-141">A literal value.</span></span>

- <span data-ttu-id="3df53-142">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="3df53-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="3df53-143">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="3df53-143">An enumeration constant.</span></span>

<span data-ttu-id="3df53-144">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="3df53-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="3df53-145">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="3df53-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="3df53-146">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="3df53-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="3df53-147">En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.</span><span class="sxs-lookup"><span data-stu-id="3df53-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="3df53-148">La búsqueda de `null` puede realizarse con el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="3df53-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="3df53-149">La palabra clave `null` es compatible con la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="3df53-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="3df53-150">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="3df53-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="3df53-151">En el ejemplo siguiente se muestra una comparación de comprobaciones `null`:</span><span class="sxs-lookup"><span data-stu-id="3df53-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="3df53-152">Patrón var</span><span class="sxs-lookup"><span data-stu-id="3df53-152">var pattern</span></span>

<span data-ttu-id="3df53-153">El patrón `var` es un comodín para cualquier tipo o valor.</span><span class="sxs-lookup"><span data-stu-id="3df53-153">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="3df53-154">El valor de *expr* siempre se asigna a una variable local del mismo tipo que el tipo de tiempo de compilación de *expr*.</span><span class="sxs-lookup"><span data-stu-id="3df53-154">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="3df53-155">El resultado de la expresión `is` es siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="3df53-155">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="3df53-156">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="3df53-156">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="3df53-157">En el ejemplo siguiente se usa el patrón var para asignar una expresión a una variable denominada `obj`.</span><span class="sxs-lookup"><span data-stu-id="3df53-157">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="3df53-158">Después, se muestra el valor y el tipo de `obj`.</span><span class="sxs-lookup"><span data-stu-id="3df53-158">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="3df53-159">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="3df53-159">C# language specification</span></span>
  
<span data-ttu-id="3df53-160">Para más información, consulte la sección del [operador is](~/_csharplang/spec/expressions.md#the-is-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y las siguientes propuestas del lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="3df53-160">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="3df53-161">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="3df53-161">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="3df53-162">Coincidencia de patrones con genéricos</span><span class="sxs-lookup"><span data-stu-id="3df53-162">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="3df53-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="3df53-163">See also</span></span>

- [<span data-ttu-id="3df53-164">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3df53-164">C# reference</span></span>](../index.md)
- [<span data-ttu-id="3df53-165">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3df53-165">C# keywords</span></span>](index.md)
- [<span data-ttu-id="3df53-166">Operadores de conversión y prueba de tipos</span><span class="sxs-lookup"><span data-stu-id="3df53-166">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
