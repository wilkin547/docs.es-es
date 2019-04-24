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
ms.openlocfilehash: 9fb57caeafde9db5759300d938a85f4abf4d05f3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672464"
---
# <a name="is-c-reference"></a><span data-ttu-id="11a8d-102">is (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="11a8d-102">is (C# Reference)</span></span>

<span data-ttu-id="11a8d-103">Comprueba si un objeto es compatible con un tipo determinado o, a partir de C# 7.0, prueba una expresión en un patrón.</span><span class="sxs-lookup"><span data-stu-id="11a8d-103">Checks if an object is compatible with a given type, or (starting with C# 7.0) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="11a8d-104">Probar la compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="11a8d-104">Testing for type compatibility</span></span>

<span data-ttu-id="11a8d-105">La palabra clave `is` evalúa la compatibilidad de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="11a8d-105">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="11a8d-106">Determina si una instancia de objeto o el resultado de una expresión se puede convertir en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="11a8d-106">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="11a8d-107">Tiene la sintaxis</span><span class="sxs-lookup"><span data-stu-id="11a8d-107">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="11a8d-108">en la que *expr* es una expresión que se evalúa como una instancia de un tipo y *type* es el nombre del tipo en el que se va a convertir el resultado de *expr*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-108">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="11a8d-109">La instrucción `is` es `true` si *expr* no es NULL y el objeto resultado de la evaluación de la expresión se pueden convertir en *type*. En caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-109">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="11a8d-110">Por ejemplo, el código siguiente determina si `obj` se puede convertir en una instancia del tipo `Person`:</span><span class="sxs-lookup"><span data-stu-id="11a8d-110">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

[!code-csharp[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]

<span data-ttu-id="11a8d-111">La instrucción `is` es verdadera si:</span><span class="sxs-lookup"><span data-stu-id="11a8d-111">The `is` statement is true if:</span></span>

- <span data-ttu-id="11a8d-112">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-112">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="11a8d-113">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-113">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="11a8d-114">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-114">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="11a8d-115">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-115">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="11a8d-116">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="11a8d-116">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="11a8d-117">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="11a8d-117">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="11a8d-118">*expr* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-118">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="11a8d-119">En el ejemplo siguiente se muestra que la expresión `is` se evalúa como `true` para cada una de estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="11a8d-119">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

[!code-csharp[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]

<span data-ttu-id="11a8d-120">La palabra clave `is` genera una advertencia en tiempo de compilación si se sabe que la expresión es siempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-120">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="11a8d-121">Solo considera las conversiones de referencias, las conversiones boxing y las conversiones unboxing. No tiene en cuenta las conversiones definidas por el usuario o las conversiones definidas por los operadores [implicit](implicit.md) y [explicit](explicit.md) de un tipo.</span><span class="sxs-lookup"><span data-stu-id="11a8d-121">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="11a8d-122">En el ejemplo siguiente se generan advertencias porque el resultado de la conversión se conoce en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="11a8d-122">The following example generates warnings because the result of the conversion is known at compile time.</span></span> <span data-ttu-id="11a8d-123">La expresión `is` para conversiones de `int` en `long` y `double` devuelve false, ya que estas conversiones se controlan mediante el operador [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="11a8d-123">The `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

[!code-csharp[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]

<span data-ttu-id="11a8d-124">`expr` no puede ser un método anónimo ni una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="11a8d-124">`expr` cannot be an anonymous method or lambda expression.</span></span> <span data-ttu-id="11a8d-125">Puede ser cualquier otra expresión que devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="11a8d-125">It can be any other expression that returns a value.</span></span> <span data-ttu-id="11a8d-126">En el ejemplo siguiente se usa `is` para evaluar el valor devuelto de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="11a8d-126">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
[!code-csharp[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]

<span data-ttu-id="11a8d-127">A partir de C# 7.0, puede usar la coincidencia de patrones con el [patrón de tipo](#type) para escribir código más conciso que use la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-127">Starting with C# 7.0, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="11a8d-128">Coincidencia de patrones con `is`</span><span class="sxs-lookup"><span data-stu-id="11a8d-128">Pattern matching with `is`</span></span>

<span data-ttu-id="11a8d-129">A partir de C# 7.0, las instrucciones `is` y [switch](../../../csharp/language-reference/keywords/switch.md) admiten la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="11a8d-129">Starting with C# 7.0, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="11a8d-130">La palabra clave `is` admite los patrones siguientes:</span><span class="sxs-lookup"><span data-stu-id="11a8d-130">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="11a8d-131">[Patrón de tipo](#type), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="11a8d-131">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="11a8d-132">[Patrón de constante](#constant), que comprueba si una expresión se evalúa como un valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="11a8d-132">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="11a8d-133">[Patrón var](#var), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.</span><span class="sxs-lookup"><span data-stu-id="11a8d-133">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <a name="a-nametype-type-pattern"></a><span data-ttu-id="11a8d-134"><a name="type" />Patrón de tipo</span><span class="sxs-lookup"><span data-stu-id="11a8d-134"><a name="type" />Type pattern</span></span>

<span data-ttu-id="11a8d-135">Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="11a8d-135">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="11a8d-136">Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa.</span><span class="sxs-lookup"><span data-stu-id="11a8d-136">It's a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="11a8d-137">La forma general del patrón de tipos `is` es:</span><span class="sxs-lookup"><span data-stu-id="11a8d-137">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="11a8d-138">donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-138">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="11a8d-139">La expresión `is` es `true` si *expr* no es `null` y se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="11a8d-139">The `is` expression is `true` if *expr* isn't `null`, and any of the following is true:</span></span>

- <span data-ttu-id="11a8d-140">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-140">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="11a8d-141">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-141">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="11a8d-142">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-142">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="11a8d-143">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-143">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="11a8d-144">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="11a8d-144">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="11a8d-145">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="11a8d-145">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="11a8d-146">*expr* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-146">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="11a8d-147">A partir de C# 7.1, *expr* puede tener un tipo de tiempo de compilación definido por un parámetro y sus restricciones.</span><span class="sxs-lookup"><span data-stu-id="11a8d-147">Beginning with C# 7.1, *expr* may have a compile-time type defined by a generic type parameter and its constraints.</span></span> 

<span data-ttu-id="11a8d-148">Si *expr* es `true` e `is` se usa con una instrucción `if`, *varname* se asigna y tiene ámbito local solo dentro de la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-148">If *expr* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="11a8d-149">En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> de tipo.</span><span class="sxs-lookup"><span data-stu-id="11a8d-149">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=nameWithType> method.</span></span>

[!code-csharp[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]

<span data-ttu-id="11a8d-150">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="11a8d-150">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="11a8d-151">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-151">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

[!code-csharp[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]

<span data-ttu-id="11a8d-152">El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="11a8d-152">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="11a8d-153">En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.</span><span class="sxs-lookup"><span data-stu-id="11a8d-153">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

[!code-csharp[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]

<span data-ttu-id="11a8d-154">El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="11a8d-154">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

[!code-csharp[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="11a8d-155"><a name="constant" /> Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="11a8d-155"><a name="constant" /> Constant pattern</span></span>

<span data-ttu-id="11a8d-156">Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="11a8d-156">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="11a8d-157">En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="11a8d-157">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="11a8d-158">A partir de C# 7.0, la instrucción `is` también lo admite.</span><span class="sxs-lookup"><span data-stu-id="11a8d-158">Starting with C# 7.0, it's supported by the `is` statement as well.</span></span> <span data-ttu-id="11a8d-159">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="11a8d-159">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="11a8d-160">donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="11a8d-160">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="11a8d-161">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="11a8d-161">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="11a8d-162">Un valor literal.</span><span class="sxs-lookup"><span data-stu-id="11a8d-162">A literal value.</span></span>

- <span data-ttu-id="11a8d-163">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="11a8d-163">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="11a8d-164">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="11a8d-164">An enumeration constant.</span></span>

<span data-ttu-id="11a8d-165">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="11a8d-165">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="11a8d-166">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="11a8d-166">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="11a8d-167">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="11a8d-167">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="11a8d-168">En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.</span><span class="sxs-lookup"><span data-stu-id="11a8d-168">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

[!code-csharp[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]

<span data-ttu-id="11a8d-169">La búsqueda de `null` puede realizarse con el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="11a8d-169">Checking for `null` can be performed using the constant pattern.</span></span> <span data-ttu-id="11a8d-170">La palabra clave `null` es compatible con la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-170">The `null` keyword is supported by the `is` statement.</span></span> <span data-ttu-id="11a8d-171">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="11a8d-171">Its syntax is:</span></span>

```csharp 
   expr is null
```

<span data-ttu-id="11a8d-172">En el ejemplo siguiente se muestra una comparación de comprobaciones `null`:</span><span class="sxs-lookup"><span data-stu-id="11a8d-172">The following example shows a comparison of `null` checks:</span></span>

[!code-csharp[is#11](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern11.cs#11)]
 
### <span data-ttu-id="11a8d-173"><a name="var" /> Patrón var </a></span><span class="sxs-lookup"><span data-stu-id="11a8d-173"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="11a8d-174">El patrón `var` es un comodín para cualquier tipo o valor.</span><span class="sxs-lookup"><span data-stu-id="11a8d-174">The `var` pattern is a catch-all for any type or value.</span></span> <span data-ttu-id="11a8d-175">El valor de *expr* siempre se asigna a una variable local del mismo tipo que el tipo de tiempo de compilación de *expr*.</span><span class="sxs-lookup"><span data-stu-id="11a8d-175">The value of *expr* is always assigned to a local variable the same type as the compile time type of *expr*.</span></span> <span data-ttu-id="11a8d-176">El resultado de la expresión `is` es siempre `true`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-176">The result of the `is` expression is always `true`.</span></span> <span data-ttu-id="11a8d-177">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="11a8d-177">Its syntax is:</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="11a8d-178">En el ejemplo siguiente se usa el patrón var para asignar una expresión a una variable denominada `obj`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-178">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="11a8d-179">Después, se muestra el valor y el tipo de `obj`.</span><span class="sxs-lookup"><span data-stu-id="11a8d-179">It then displays the value and the type of `obj`.</span></span>

[!code-csharp[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="11a8d-180">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="11a8d-180">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="11a8d-181">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a8d-181">See also</span></span>

- [<span data-ttu-id="11a8d-182">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="11a8d-182">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="11a8d-183">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="11a8d-183">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="11a8d-184">typeof</span><span class="sxs-lookup"><span data-stu-id="11a8d-184">typeof</span></span>](../../../csharp/language-reference/keywords/typeof.md)
- [<span data-ttu-id="11a8d-185">as</span><span class="sxs-lookup"><span data-stu-id="11a8d-185">as</span></span>](../../../csharp/language-reference/keywords/as.md)
- [<span data-ttu-id="11a8d-186">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="11a8d-186">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
