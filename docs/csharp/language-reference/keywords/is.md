---
title: is (Referencia de C#)
keywords: Palabra clave is (C#), is (C#)
ms.date: 2017-02-17
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- is_CSharpKeyword
- is
dev_langs:
- CSharp
helpviewer_keywords:
- is keyword [C#]
ms.assetid: bc62316a-d41f-4f90-8300-c6f4f0556e43
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58b18284b12ca0c636ed3fa923c43d94f202597f
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="is-c-reference"></a><span data-ttu-id="18231-103">is (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="18231-103">is (C# Reference)</span></span> #

<span data-ttu-id="18231-104">Comprueba si un objeto es compatible con un tipo determinado o, a partir de C# 7, comprueba una expresión con un patrón.</span><span class="sxs-lookup"><span data-stu-id="18231-104">Checks if an object is compatible with a given type, or (starting with C# 7) tests an expression against a pattern.</span></span>

## <a name="testing-for-type-compatibility"></a><span data-ttu-id="18231-105">Probar la compatibilidad de tipos</span><span class="sxs-lookup"><span data-stu-id="18231-105">Testing for type compatibility</span></span> ##

<span data-ttu-id="18231-106">La palabra clave `is` evalúa la compatibilidad de tipos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18231-106">The `is` keyword evaluates type compatibility at runtime.</span></span> <span data-ttu-id="18231-107">Determina si una instancia de objeto o el resultado de una expresión se puede convertir en un tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="18231-107">It determines whether an object instance or the result of an expression can be converted to a specified type.</span></span> <span data-ttu-id="18231-108">Tiene la sintaxis</span><span class="sxs-lookup"><span data-stu-id="18231-108">It has the syntax</span></span>

```csharp
   expr is type
```

<span data-ttu-id="18231-109">en la que *expr* es una expresión que se evalúa como una instancia de un tipo y *type* es el nombre del tipo en el que se va a convertir el resultado de *expr*.</span><span class="sxs-lookup"><span data-stu-id="18231-109">where *expr* is an expression that evaluates to an instance of some type, and *type* is the name of the type to which the result of *expr* is to be converted.</span></span> <span data-ttu-id="18231-110">La instrucción `is` es `true` si *expr* no es NULL y el objeto resultado de la evaluación de la expresión se pueden convertir en *type*. En caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="18231-110">The `is` statement is `true` if *expr* is non-null and the object that results from evaluating the expression can be converted to *type*; otherwise, it returns `false`.</span></span>

<span data-ttu-id="18231-111">Por ejemplo, el código siguiente determina si `obj` se puede convertir en una instancia del tipo `Person`:</span><span class="sxs-lookup"><span data-stu-id="18231-111">For example, the following code determines if `obj` can be cast to an instance of the `Person` type:</span></span>

<span data-ttu-id="18231-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="18231-112">[!code-cs[is#1](../../../../samples/snippets/csharp/language-reference/keywords/is/is1.cs#1)]</span></span>

<span data-ttu-id="18231-113">La instrucción `is` es verdadera si:</span><span class="sxs-lookup"><span data-stu-id="18231-113">The `is` statement is true if:</span></span>

- <span data-ttu-id="18231-114">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-114">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="18231-115">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-115">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="18231-116">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-116">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="18231-117">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-117">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="18231-118">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="18231-118">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="18231-119">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="18231-119">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="18231-120">*expr* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-120">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="18231-121">En el ejemplo siguiente se muestra que la expresión `is` se evalúa como `true` para cada una de estas conversiones.</span><span class="sxs-lookup"><span data-stu-id="18231-121">The following example shows that the `is` expression evaluates to `true` for each of these conversions.</span></span>

<span data-ttu-id="18231-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span><span class="sxs-lookup"><span data-stu-id="18231-122">[!code-cs[is#3](../../../../samples/snippets/csharp/language-reference/keywords/is/is3.cs#3)]</span></span>

<span data-ttu-id="18231-123">La palabra clave `is` genera una advertencia en tiempo de compilación si se sabe que la expresión es siempre `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="18231-123">The `is` keyword generates a compile-time warning if the expression is known to always be either `true` or `false`.</span></span> <span data-ttu-id="18231-124">Solo considera las conversiones de referencias, las conversiones boxing y las conversiones unboxing. No tiene en cuenta las conversiones definidas por el usuario o las conversiones definidas por los operadores [implicit](implicit.md) y [explicit](explicit.md) de un tipo.</span><span class="sxs-lookup"><span data-stu-id="18231-124">It only considers reference conversions, boxing conversions, and unboxing conversions; it does not consider user-defined conversions or conversions defined by a type's [implicit](implicit.md) and [explicit](explicit.md) operators.</span></span> <span data-ttu-id="18231-125">En el ejemplo siguiente se generan advertencias porque el resultado de la conversión se conoce en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="18231-125">The following example generates warnings because the result of the conversion is known at compile-time.</span></span> <span data-ttu-id="18231-126">Tenga en cuenta que la expresión `is` para conversiones de `int` en `long` y `double` devuelve false, ya que estas conversiones se controlan mediante el operador [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="18231-126">Note that the `is` expression for conversions from `int` to `long` and `double` return false, since these conversions are handled by the [implicit](implicit.md) operator.</span></span>

<span data-ttu-id="18231-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="18231-127">[!code-cs[is#2](../../../../samples/snippets/csharp/language-reference/keywords/is/is2.cs#2)]</span></span>

<span data-ttu-id="18231-128">`expr` puede ser cualquier expresión que devuelva un valor, a excepción de métodos anónimos y expresiones lambda.</span><span class="sxs-lookup"><span data-stu-id="18231-128">`expr` can be any expression that returns a value, with the exception of anonymous methods and lambda expressions.</span></span> <span data-ttu-id="18231-129">En el ejemplo siguiente se usa `is` para evaluar el valor devuelto de una llamada de método.</span><span class="sxs-lookup"><span data-stu-id="18231-129">The following example uses  `is` to evaluate the return value of a method call.</span></span>   
<span data-ttu-id="18231-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span><span class="sxs-lookup"><span data-stu-id="18231-130">[!code-cs[is#4](../../../../samples/snippets/csharp/language-reference/keywords/is/is4.cs#4)]</span></span>

<span data-ttu-id="18231-131">A partir de C# 7, puede usar la coincidencia de patrones con el [patrón de tipo](#type) para escribir código más conciso que use la instrucción `is`.</span><span class="sxs-lookup"><span data-stu-id="18231-131">Starting with C# 7, you can use pattern matching with the [type pattern](#type) to write more concise code that uses the `is` statement.</span></span>

## <a name="pattern-matching-with-is"></a><span data-ttu-id="18231-132">Coincidencia de patrones con `is`</span><span class="sxs-lookup"><span data-stu-id="18231-132">Pattern matching with `is`</span></span> ##

<span data-ttu-id="18231-133">A partir de C# 7, las instrucciones `is` y [switch](../../../csharp/language-reference/keywords/switch.md) admiten la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="18231-133">Starting with C# 7, the `is` and [switch](../../../csharp/language-reference/keywords/switch.md) statements support pattern matching.</span></span> <span data-ttu-id="18231-134">La palabra clave `is` admite los patrones siguientes:</span><span class="sxs-lookup"><span data-stu-id="18231-134">The `is` keyword supports the following patterns:</span></span>

- <span data-ttu-id="18231-135">[Patrón de tipo](#type), que comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="18231-135">[Type pattern](#type),  which tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span>

- <span data-ttu-id="18231-136">[Patrón de constante](#constant), que comprueba si una expresión se evalúa como un valor constante especificado.</span><span class="sxs-lookup"><span data-stu-id="18231-136">[Constant pattern](#constant), which tests whether an expression evaluates to a specified constant value.</span></span>

- <span data-ttu-id="18231-137">[Patrón var](#var), una coincidencia que siempre se realiza correctamente y enlaza el valor de una expresión a una variable local nueva.</span><span class="sxs-lookup"><span data-stu-id="18231-137">[var pattern](#var), a match that always succeeds and binds the value of an expression to a new local variable.</span></span> 

### <span data-ttu-id="18231-138"><a name="type" /> Patrón de tipo </a></span><span class="sxs-lookup"><span data-stu-id="18231-138"><a name="type" /> Type pattern </a></span></span>

<span data-ttu-id="18231-139">Cuando se usa el patrón de tipo para realizar la coincidencia de patrones, `is` comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="18231-139">When using the type pattern to perform pattern matching, `is` tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="18231-140">Es una extensión sencilla de la instrucción `is` que habilita la evaluación y la conversión de tipos concisa.</span><span class="sxs-lookup"><span data-stu-id="18231-140">It is a straightforward extension of the `is` statement that enables concise type evaluation and conversion.</span></span> <span data-ttu-id="18231-141">La forma general del patrón de tipos `is` es:</span><span class="sxs-lookup"><span data-stu-id="18231-141">The general form of the `is` type pattern is:</span></span>

```csharp
   expr is type varname 
```

<span data-ttu-id="18231-142">donde *expr* es una expresión que se evalúa como una instancia de un tipo, *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si la prueba `is` es `true`.</span><span class="sxs-lookup"><span data-stu-id="18231-142">where *expr* is an expression that evaluates to an instance of some type, *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the `is` test is `true`.</span></span> 

<span data-ttu-id="18231-143">La expresión `is` es `true` si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="18231-143">The `is` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="18231-144">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-144">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="18231-145">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-145">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="18231-146">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-146">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="18231-147">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-147">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="18231-148">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración.</span><span class="sxs-lookup"><span data-stu-id="18231-148">The *compile-time type* of a variable is the variable's type as defined in its declaration.</span></span> <span data-ttu-id="18231-149">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="18231-149">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="18231-150">*expr* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="18231-150">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="18231-151">Si *exp* es `true` e `is` se usa con una instrucción `if`, *varname* se asigna y tiene ámbito local solo dentro de la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="18231-151">If *exp* is `true` and `is` is used with an `if` statement, *varname* is assigned and has local scope within the `if` statement only.</span></span>

<span data-ttu-id="18231-152">En el ejemplo siguiente se usa el patrón de tipo `is` para proporcionar la implementación de un método <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> de tipo.</span><span class="sxs-lookup"><span data-stu-id="18231-152">The following example uses the `is` type pattern to provide the implementation of a type's <xref:System.IComparable.CompareTo(System.Object)?displayProperty=fullName> method.</span></span>

<span data-ttu-id="18231-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span><span class="sxs-lookup"><span data-stu-id="18231-153">[!code-cs[is#5](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern5.cs#5)]</span></span>

<span data-ttu-id="18231-154">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="18231-154">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="18231-155">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null`.</span><span class="sxs-lookup"><span data-stu-id="18231-155">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null`.</span></span>  

<span data-ttu-id="18231-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span><span class="sxs-lookup"><span data-stu-id="18231-156">[!code-cs[is#6](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern6.cs#6)]</span></span>

<span data-ttu-id="18231-157">El patrón de tipo `is` también genera código más compacto al determinar el tipo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="18231-157">The `is` type pattern also produces more compact code when determining the type of a value type.</span></span> <span data-ttu-id="18231-158">En el ejemplo siguiente se usa el patrón de tipo `is` para determinar si un objeto es una instancia de `Person` o `Dog` antes de mostrar el valor de una propiedad adecuada.</span><span class="sxs-lookup"><span data-stu-id="18231-158">The following example uses the `is` type pattern to determine whether an object is a `Person` or a `Dog` instance before displaying the value of an appropriate property.</span></span> 

<span data-ttu-id="18231-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span><span class="sxs-lookup"><span data-stu-id="18231-159">[!code-cs[is#9](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern9.cs#9)]</span></span>

<span data-ttu-id="18231-160">El código equivalente sin coincidencia de patrones requiere una asignación independiente que incluya una conversión explícita.</span><span class="sxs-lookup"><span data-stu-id="18231-160">The equivalent code without pattern matching requires a separate assignment that includes an explicit cast.</span></span>

<span data-ttu-id="18231-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span><span class="sxs-lookup"><span data-stu-id="18231-161">[!code-cs[is#10](../../../../samples/snippets/csharp/language-reference/keywords/is/is-type-pattern10.cs#10)]</span></span>

### <a name="a-nameconstant--constant-pattern"></a><span data-ttu-id="18231-162"><a name="constant" /> Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="18231-162"><a name="constant" /> Constant pattern</span></span> ###

<span data-ttu-id="18231-163">Al realizar la coincidencia de patrones con el patrón constante, `is` comprueba si una expresión es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="18231-163">When performing pattern matching with the constant pattern, `is` tests whether an expression equals a specified constant.</span></span> <span data-ttu-id="18231-164">En C# 6 y versiones anteriores, la instrucción [switch](switch.md) admite el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="18231-164">In C# 6 and earlier versions, the constant pattern is supported by the [switch](switch.md) statement.</span></span> <span data-ttu-id="18231-165">A partir de C# 7, la instrucción `is` también lo admite.</span><span class="sxs-lookup"><span data-stu-id="18231-165">Starting with C# 7, it is supported by the `is` statement as well.</span></span> <span data-ttu-id="18231-166">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="18231-166">Its syntax is:</span></span>

```csharp
   expr is constant
```

<span data-ttu-id="18231-167">donde *expr* es la expresión que se va a evaluar y *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="18231-167">where *expr* is the expression to evaluate, and *constant* is the value to test for.</span></span> <span data-ttu-id="18231-168">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="18231-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="18231-169">Un valor literal.</span><span class="sxs-lookup"><span data-stu-id="18231-169">A literal value.</span></span>

- <span data-ttu-id="18231-170">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="18231-170">The name of a declared `const` variable.</span></span>

- <span data-ttu-id="18231-171">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="18231-171">An enumeration constant.</span></span>

<span data-ttu-id="18231-172">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="18231-172">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="18231-173">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="18231-173">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="18231-174">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="18231-174">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="18231-175">En el ejemplo siguiente se combinan los patrones de tipo y de constante para probar si un objeto es una instancia de `Dice` y, si es así, para determinar si el valor de una tirada de dados es 6.</span><span class="sxs-lookup"><span data-stu-id="18231-175">The following example combines the type and constant patterns to test whether an object is a `Dice` instance and, if it is, to determine whether the value of a dice roll is 6.</span></span>

<span data-ttu-id="18231-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span><span class="sxs-lookup"><span data-stu-id="18231-176">[!code-cs[is#7](../../../../samples/snippets/csharp/language-reference/keywords/is/is-const-pattern7.cs#7)]</span></span>
 
### <span data-ttu-id="18231-177"><a name="var" /> Patrón var </a></span><span class="sxs-lookup"><span data-stu-id="18231-177"><a name="var" /> var pattern </a></span></span>

<span data-ttu-id="18231-178">Una coincidencia de patrones con el patrón de var siempre se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="18231-178">A pattern match with the var pattern always succeeds.</span></span> <span data-ttu-id="18231-179">Su sintaxis es</span><span class="sxs-lookup"><span data-stu-id="18231-179">Its syntax is</span></span>

```csharp 
   expr is var varname
```

<span data-ttu-id="18231-180">donde el valor de *expr* siempre se asigna a una variable local denominada *varname*.</span><span class="sxs-lookup"><span data-stu-id="18231-180">where the value of *expr* is always assigned to a local variable named *varname*.</span></span> <span data-ttu-id="18231-181">*varname* es una variable estática del mismo tipo que *expr*.</span><span class="sxs-lookup"><span data-stu-id="18231-181">*varname* is a static variable of the same type as *expr*.</span></span> <span data-ttu-id="18231-182">En el ejemplo siguiente se usa el patrón var para asignar una expresión a una variable denominada `obj`.</span><span class="sxs-lookup"><span data-stu-id="18231-182">The following example uses the var pattern to assign an expression to a variable named `obj`.</span></span> <span data-ttu-id="18231-183">Después, se muestra el valor y el tipo de `obj`.</span><span class="sxs-lookup"><span data-stu-id="18231-183">It then displays the value and the type of `obj`.</span></span>

<span data-ttu-id="18231-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span><span class="sxs-lookup"><span data-stu-id="18231-184">[!code-cs[is#8](../../../../samples/snippets/csharp/language-reference/keywords/is/is-var-pattern8.cs#8)]</span></span>

<span data-ttu-id="18231-185">Observe que si *expr* es `null`, la expresión `is` sigue siendo true y asigna `null` a *varname*.</span><span class="sxs-lookup"><span data-stu-id="18231-185">Note that if *expr* is `null`, the `is` expression still is true and assigns `null` to *varname*.</span></span> 

# <a name="c-language-specification"></a><span data-ttu-id="18231-186">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="18231-186">C# Language Specification</span></span>
  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="18231-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="18231-187">See also</span></span>  
 <span data-ttu-id="18231-188">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="18231-188">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="18231-189">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="18231-189">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="18231-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span><span class="sxs-lookup"><span data-stu-id="18231-190">[typeof](../../../csharp/language-reference/keywords/typeof.md) </span></span>  
 <span data-ttu-id="18231-191">[as](../../../csharp/language-reference/keywords/as.md) </span><span class="sxs-lookup"><span data-stu-id="18231-191">[as](../../../csharp/language-reference/keywords/as.md) </span></span>  
 [<span data-ttu-id="18231-192">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="18231-192">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

