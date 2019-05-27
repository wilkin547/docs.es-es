---
title: 'is: Referencia de C#'
ms.custom: seodec18
ms.date: 04/09/2019
f1_keywords:
- is_CSharpKeyword
- is
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
ms.openlocfilehash: 79cc59eb8de513f547a8fd87db8c95dd9af37375
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754519"
---
# <a name="is-c-reference"></a><span data-ttu-id="ed1f5-102">is (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ed1f5-102">is (C# Reference)</span></span>

<span data-ttu-id="ed1f5-103">Comprueba si un objeto es compatible con un tipo determinado o, a partir de C# 7.0, prueba una expresión en un patrón.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="ed1f5-104">Probar la compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="ed1f5-104">Testing for type compatibility</span></span>

<span data-ttu-id="ed1f5-105">La palabra clave `is` evalúa la compatibilidad de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="ed1f5-106">Determina si una instancia de objeto o el resultado de una expresión se puede convertir en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="ed1f5-107">Tiene la sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed1f5-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="ed1f5-108">en la que *expr* es una expresión que se evalúa como una instancia de un tipo y *type* es el nombre del tipo en el que se va a convertir el resultado de *expr*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="ed1f5-109">La instrucción `is` es `true` si *expr* no es NULL y el objeto resultado de la evaluación de la expresión se pueden convertir en *type*. En caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="ed1f5-110">Por ejemplo, el código siguiente determina si `obj` se puede convertir en una instancia del tipo `Person`:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="ed1f5-111">La instrucción `is` es verdadera si:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="ed1f5-112">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="ed1f5-113">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="ed1f5-114">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="ed1f5-115">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="ed1f5-116">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="ed1f5-117">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="ed1f5-118">*expr* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="ed1f5-119">En el ejemplo siguiente se muestra que la expresión `is` se evalúa como `true` para cada una de estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="ed1f5-120">La palabra clave `is` genera una advertencia en tiempo de compilación si se sabe que la expresión es siempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="ed1f5-121">Solo considera las conversiones de referencias, las conversiones boxing y las conversiones unboxing. No tiene en cuenta las conversiones definidas por el usuario o las conversiones definidas por los operadores [implicit](implicit.md) y [explicit](explicit.md) de un tipo.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="ed1f5-122">En el ejemplo siguiente se generan advertencias porque el resultado de la conversión se conoce en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="ed1f5-123">La expresión `is` para conversiones de `int` en `long` y `double` devuelve false, ya que estas conversiones se controlan mediante el operador [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="ed1f5-124">`expr` no puede ser un método anónimo ni una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="ed1f5-125">Puede ser cualquier otra expresión que devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="ed1f5-126">En el ejemplo siguiente se usa `is` para evaluar el valor devuelto de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="ed1f5-127">A partir de C# 7.0, puede usar la coincidencia de patrones con el [patrón de tipo](#type) para escribir código más conciso que use la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="ed1f5-128">Coincidencia de patrones con `is`</span><span class="sxs-lookup"><span data-stu-id="ed1f5-128">Pattern matching with `is`</span></span>

<span data-ttu-id="ed1f5-129">A partir de C# 7.0, las instrucciones `is` y [switch](../../../csharp/language-reference/keywords/switch.md) admiten la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="ed1f5-130">La palabra clave `is` admite los patrones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="ed1f5-131">[Patrón de tipo](#type), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="ed1f5-132">[Patrón de constante](#constant), que comprueba si una expresión se evalúa como un valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="ed1f5-133">[Patrón var](#var), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="ed1f5-134"><a name="type" />Patrón de tipo</span><span class="sxs-lookup"><span data-stu-id="ed1f5-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="ed1f5-135">Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="ed1f5-136">Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="ed1f5-137">La forma general del patrón de tipos `is` es:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="ed1f5-138">donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="ed1f5-139">La expresión `is` es `true` si *expr* no es `null` y se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="ed1f5-140">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="ed1f5-141">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="ed1f5-142">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="ed1f5-143">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="ed1f5-144">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="ed1f5-145">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="ed1f5-146">*type* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="ed1f5-147">A partir de C# 7.1, *expr* puede tener un tipo de tiempo de compilación definido por un parámetro y sus restricciones.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="ed1f5-148">Si *expr* es `true` y `is` se usa con una instrucción `if`, solo se asigna *varname* dentro de la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned within the `if` statement only.</span></span> <span data-ttu-id="ed1f5-149">El ámbito de *varname* abarca de la expresión `is` al final del bloque que incluye la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-149">The scope of *varname* is from the `is` expression to the end of the block enclosing the `if` statement.</span></span> <span data-ttu-id="ed1f5-150">El uso de *varname* en cualquier otra ubicación genera un error en tiempo de compilación por el uso de una variable que no se ha asignado.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-150">Using *varname* in any other location generates a compile-time error for use of a variable that has not been assigned.</span></span>

<span data-ttu-id="ed1f5-151">En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de tipo.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-151">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="ed1f5-152">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-152">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="ed1f5-153">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-153">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="ed1f5-154">El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-154">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="ed1f5-155">En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-155">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="ed1f5-156">El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-156">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="ed1f5-157"><a name="constant" /> Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="ed1f5-157"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="ed1f5-158">Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-158">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="ed1f5-159">En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-159">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="ed1f5-160">A partir de C# 7.0, la instrucción `is` también lo admite.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-160">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="ed1f5-161">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-161">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="ed1f5-162">donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-162">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="ed1f5-163">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-163">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="ed1f5-164">Un valor literal.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-164">A literal value.</span></span>

- <span data-ttu-id="ed1f5-165">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-165">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="ed1f5-166">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-166">An enumeration constant.</span></span>

<span data-ttu-id="ed1f5-167">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-167">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="ed1f5-168">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-168">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="ed1f5-169">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="ed1f5-169">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="ed1f5-170">En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-170">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="ed1f5-171">La búsqueda de `null` puede realizarse con el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-171">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="ed1f5-172">La palabra clave `null` es compatible con la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-172">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="ed1f5-173">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-173">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="ed1f5-174">En el ejemplo siguiente se muestra una comparación de comprobaciones `null`:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-174">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="ed1f5-175"><a name="var" /> Patrón var </a></span><span class="sxs-lookup"><span data-stu-id="ed1f5-175"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="ed1f5-176">El patrón `var` es un comodín para cualquier tipo o valor.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-176">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="ed1f5-177">El valor de *expr* siempre se asigna a una variable local del mismo tipo que el tipo de tiempo de compilación de *expr*.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-177">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="ed1f5-178">El resultado de la expresión `is` es siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-178">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="ed1f5-179">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="ed1f5-179">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="ed1f5-180">En el ejemplo siguiente se usa el patrón var para asignar una expresión a una variable denominada `obj`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-180">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="ed1f5-181">Después, se muestra el valor y el tipo de `obj`.</span><span class="sxs-lookup"><span data-stu-id="ed1f5-181">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="ed1f5-182">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-182">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ed1f5-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed1f5-183">See also</span></span>

- [<span data-ttu-id="ed1f5-184">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-184">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="ed1f5-185">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ed1f5-185">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="ed1f5-186">typeof</span><span class="sxs-lookup"><span data-stu-id="ed1f5-186">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="ed1f5-187">as</span><span class="sxs-lookup"><span data-stu-id="ed1f5-187">as</span></span>](../../../csharp/language-reference/keywords/as.md)
- [<span data-ttu-id="ed1f5-188">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="ed1f5-188">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
