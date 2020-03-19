---
title: 'is: Referencia de C#'
ms.date: 06/21/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: e64b690482419963a92764b2c97a42dbb231fbfc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398308"
---
# <a name="is-c-reference"></a><span data-ttu-id="0e4c8-102">is (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0e4c8-102">is (C# Reference)</span></span>

<span data-ttu-id="0e4c8-103">El operador `is` comprueba si el resultado de una expresión es compatible con un tipo determinado o, a partir de C# 7.0, prueba una expresión en un patrón.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-103">The `is` operator checks if the result of an expression is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span> <span data-ttu-id="0e4c8-104">Para obtener información sobre el operador de prueba de tipos `is`, consulte la sección [operador is](../operators/type-testing-and-cast.md#is-operator) del artículo [Operadores de conversión y prueba de tipos](../operators/type-testing-and-cast.md).</span><span class="sxs-lookup"><span data-stu-id="0e4c8-104">For information about the type-testing `is` operator see the [is operator](../operators/type-testing-and-cast.md#is-operator) section of the [Type-testing and cast operators](../operators/type-testing-and-cast.md) article.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="0e4c8-105">Coincidencia de patrones con `is`</span><span class="sxs-lookup"><span data-stu-id="0e4c8-105">Pattern matching with `is`</span></span>

<span data-ttu-id="0e4c8-106">A partir de C# 7.0, las instrucciones `is` y [switch](switch.md) admiten la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-106">Starting with C# 7.0, the `is` and [switch](switch.md) statements support pattern matching.</span></span> <span data-ttu-id="0e4c8-107">La palabra clave `is` admite los patrones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-107">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="0e4c8-108">[Patrón de tipo](#type-pattern), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-108">[Type pattern](#type-pattern), which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="0e4c8-109">[Patrón de constante](#constant-pattern), que comprueba si una expresión se evalúa como un valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-109">[Constant pattern](#constant-pattern), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="0e4c8-110">[Patrón var](#var-pattern), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-110">[var pattern](#var-pattern), a match that always succeeds and binds the value of an expression to a new local variable.</span></span>

### <a name="type-pattern"></a><span data-ttu-id="0e4c8-111">Patrón de tipo</span><span class="sxs-lookup"><span data-stu-id="0e4c8-111">Type pattern</span></span>

<span data-ttu-id="0e4c8-112">Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-112">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="0e4c8-113">Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-113">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="0e4c8-114">La forma general del patrón de tipos `is` es:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-114">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname
```

<span data-ttu-id="0e4c8-115">Donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-115">Where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span>

<span data-ttu-id="0e4c8-116">La expresión `is` es `true` si *expr* no es `null` y se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-116">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="0e4c8-117">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-117">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="0e4c8-118">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-118">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="0e4c8-119">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-119">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="0e4c8-120">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-120">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="0e4c8-121">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-121">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="0e4c8-122">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-122">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="0e4c8-123">*type* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-123">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="0e4c8-124">A partir de C# 7.1, *expr* puede tener un tipo de tiempo de compilación definido por un parámetro y sus restricciones.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-124">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span>

<span data-ttu-id="0e4c8-125">Si *expr* es `true` y `is` se usa con una instrucción `if`, solo se asigna *varname* dentro de la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-125">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="0e4c8-126">El ámbito de *varname* abarca de la expresión `is` al final del bloque que incluye la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-126">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="0e4c8-127">El uso de *varname* en cualquier otra ubicación genera un error en tiempo de compilación por el uso de una variable que no se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-127">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="0e4c8-128">En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de tipo.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-128">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="0e4c8-129">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-129">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="0e4c8-130">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-130">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="0e4c8-131">El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-131">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="0e4c8-132">En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-132">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span>

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="0e4c8-133">El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-133">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="constant-pattern"></a><span data-ttu-id="0e4c8-134">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="0e4c8-134">Constant pattern</span></span>

<span data-ttu-id="0e4c8-135">Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-135">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="0e4c8-136">En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-136">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="0e4c8-137">A partir de C# 7.0, la instrucción `is` también lo admite.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-137">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="0e4c8-138">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-138">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="0e4c8-139">donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-139">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="0e4c8-140">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-140">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="0e4c8-141">Un valor literal.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-141">A literal value.</span></span>

- <span data-ttu-id="0e4c8-142">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-142">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="0e4c8-143">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-143">An enumeration constant.</span></span>

<span data-ttu-id="0e4c8-144">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-144">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="0e4c8-145">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="0e4c8-145">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="0e4c8-146">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="0e4c8-146">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="0e4c8-147">En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-147">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="0e4c8-148">La búsqueda de `null` puede realizarse con el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-148">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="0e4c8-149">La palabra clave `null` es compatible con la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-149">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="0e4c8-150">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-150">Its syntax is:</span></span>

```csharp
   expr is null
```

<span data-ttu-id="0e4c8-151">En el ejemplo siguiente se muestra una comparación de comprobaciones `null`:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-151">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]

### <a name="var-pattern"></a><span data-ttu-id="0e4c8-152">Patrón var</span><span class="sxs-lookup"><span data-stu-id="0e4c8-152">var pattern</span></span>

<span data-ttu-id="0e4c8-153">Una coincidencia de patrones con el patrón `var` siempre se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-153">A pattern match with the `var` pattern always succeeds.</span></span> <span data-ttu-id="0e4c8-154">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-154">Its syntax is:</span></span>

```csharp
   expr is var varname
```

<span data-ttu-id="0e4c8-155">Donde el valor de *expr* siempre se asigna a una variable local denominada *varname*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-155">Where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="0e4c8-156">*varname* es una variable del mismo tipo que el tipo en tiempo de compilación de *expr*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-156">*varname* is a variable of the same type as the compile-time type of *expr*.</span></span>

<span data-ttu-id="0e4c8-157">Si *expr* se evalúa como `null`, la expresión de `is` produce `true` y asigna `null` a *varname*.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-157">If *expr* evaluates to `null`, the `is` expression produces `true` and assigns `null` to *varname*.</span></span> <span data-ttu-id="0e4c8-158">El patrón var es uno de los pocos usos de `is` que produce `true` con un valor `null`.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-158">The var pattern is one of the few uses of `is` that produces `true` for a `null` value.</span></span>

<span data-ttu-id="0e4c8-159">El patrón `var` se puede usar para crear una variable temporal dentro de una expresión booleana, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-159">You can use the `var` pattern to create a temporary variable within a Boolean expression, as the following example shows:</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

<span data-ttu-id="0e4c8-160">En el ejemplo anterior, la variable temporal se usa para almacenar el resultado de una operación costosa.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-160">In the preceding example, the temporary variable is used to store the result of an expensive operation.</span></span> <span data-ttu-id="0e4c8-161">Tras ello, la variable se puede usar varias veces.</span><span class="sxs-lookup"><span data-stu-id="0e4c8-161">The variable can then be used multiple times.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="0e4c8-162">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="0e4c8-162">C# language specification</span></span>
  
<span data-ttu-id="0e4c8-163">Para más información, consulte la sección del [operador is](~/_csharplang/spec/expressions.md#the-is-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y las siguientes propuestas del lenguaje C#:</span><span class="sxs-lookup"><span data-stu-id="0e4c8-163">For more information, see [The is operator](~/_csharplang/spec/expressions.md#the-is-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the following C# language proposals:</span></span>

- [<span data-ttu-id="0e4c8-164">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="0e4c8-164">Pattern matching</span></span>](~/_csharplang/proposals/csharp-7.0/pattern-matching.md)
- [<span data-ttu-id="0e4c8-165">Coincidencia de patrones con genéricos</span><span class="sxs-lookup"><span data-stu-id="0e4c8-165">Pattern matching with generics</span></span>](~/_csharplang/proposals/csharp-7.1/generics-pattern-match.md)
  
## <a name="see-also"></a><span data-ttu-id="0e4c8-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e4c8-166">See also</span></span>

- [<span data-ttu-id="0e4c8-167">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0e4c8-167">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0e4c8-168">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="0e4c8-168">C# keywords</span></span>](index.md)
- [<span data-ttu-id="0e4c8-169">Operadores de conversión y prueba de tipos</span><span class="sxs-lookup"><span data-stu-id="0e4c8-169">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
