---
title: Palabra clave switch (Referencia de C#)
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
caps.latest.revision: 47
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 387c8c7e44ab818ca97e686330746f50df091bb9
ms.openlocfilehash: 5c151e3bbd46212f1234d46ff05d389f2384ca0e
ms.contentlocale: es-es
ms.lasthandoff: 08/01/2017

---
# <a name="switch-c-reference"></a><span data-ttu-id="c2cf7-102">switch (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c2cf7-102">switch (C# Reference)</span></span>
<span data-ttu-id="c2cf7-103">`switch` es una instrucción de selección que elige una sola *sección switch* para ejecutarla desde una lista de candidatos en función de una coincidencia de patrones con la *expresión de coincidencia*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span> 
  
 <span data-ttu-id="c2cf7-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-104">[!code-cs[switch#1](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]</span></span>  

<span data-ttu-id="c2cf7-105">La instrucción `switch` se suele usar como alternativa a un constructor [if-else](if-else.md) si una sola expresión se prueba con tres o más condiciones.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-105">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="c2cf7-106">Por ejemplo, la siguiente instrucción `switch` determina si una variable de tipo `Color` tiene uno de tres valores:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-106">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span> 

<span data-ttu-id="c2cf7-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-107">[!code-cs[switch#3](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]</span></span> 

<span data-ttu-id="c2cf7-108">Es equivalente al siguiente ejemplo que usa un constructor `if`-`else`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-108">It is equivalent to the following example that uses an `if`-`else` construct.</span></span> 

<span data-ttu-id="c2cf7-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-109">[!code-cs[switch#3a](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]</span></span> 

## <a name="the-match-expression"></a><span data-ttu-id="c2cf7-110">Expresión de coincidencia</span><span class="sxs-lookup"><span data-stu-id="c2cf7-110">The match expression</span></span>

<span data-ttu-id="c2cf7-111">La expresión de coincidencia proporciona el valor que debe coincidir con los patrones de las etiquetas `case`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-111">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="c2cf7-112">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-112">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="c2cf7-113">En C# 6, la expresión de coincidencia debe ser una expresión que devuelva un valor de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-113">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="c2cf7-114">Un [carácter](char.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-114">a [char](char.md).</span></span>
- <span data-ttu-id="c2cf7-115">Una [cadena](string.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-115">a [string](string.md).</span></span>
- <span data-ttu-id="c2cf7-116">Un [booleano](bool.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-116">a [bool](bool.md).</span></span> 
- <span data-ttu-id="c2cf7-117">Un valor entero, como [int](int.md) o [long](long.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-117">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="c2cf7-118">Un valor [enum](enum.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-118">an [enum](enum.md) value.</span></span>

<span data-ttu-id="c2cf7-119">A partir de C# 7, la expresión de coincidencia puede ser cualquier expresión que no sea nula.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-119">Starting with C# 7, the match expression can be any non-null expression.</span></span>
 
## <a name="the-switch-section"></a><span data-ttu-id="c2cf7-120">Sección switch</span><span class="sxs-lookup"><span data-stu-id="c2cf7-120">The switch section</span></span>
 
 <span data-ttu-id="c2cf7-121">Una instrucción `switch` incluye una o más secciones switch.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-121">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="c2cf7-122">Cada sección switch contiene una o más *etiquetas case* seguidas de una o más instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-122">Each switch section contains one or more *case labels* followed by one or more statements.</span></span> <span data-ttu-id="c2cf7-123">En el ejemplo siguiente se muestra una instrucción `switch` simple con tres secciones switch.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-123">The following example shows a simple `switch` statement that has three switch sections.</span></span> <span data-ttu-id="c2cf7-124">Cada sección switch tiene una etiqueta case, por ejemplo, `case 1:`, y dos instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-124">Each switch section has one case label, such as `case 1:`, and two statements.</span></span>
 
  <span data-ttu-id="c2cf7-125">Una instrucción `switch` puede incluir cualquier número de secciones switch y cada sección puede tener una o más etiquetas case, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-125">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="c2cf7-126">Pero dos etiquetas case no pueden contener la misma expresión.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-126">However, no two case labels may contain the same expression.</span></span>  

 <span data-ttu-id="c2cf7-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-127">[!code-cs[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]</span></span>  

 <span data-ttu-id="c2cf7-128">Solo se ejecuta una sección switch en una instrucción switch.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-128">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="c2cf7-129">C# no permite que la ejecución continúe de una sección switch a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-129">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="c2cf7-130">Por este motivo, el código siguiente genera un error del compilador, CS0163: "El control no puede pasar explícitamente de una etiqueta case (<case label>) a otra".</span><span class="sxs-lookup"><span data-stu-id="c2cf7-130">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (<case label>) to another."</span></span>   

```csharp  
switch (caseSwitch)  
{  
    // The following switch section causes an error.  
    case 1:  
        Console.WriteLine("Case 1...");  
        // Add a break or other jump statement here.  
    case 2:  
        Console.WriteLine("... and/or Case 2");  
        break;  
}  
```  
<span data-ttu-id="c2cf7-131">Este requisito se suele cumplir al salir explícitamente de la sección switch mediante una instrucción [break](break.md), [goto](goto.md) o [return](return.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-131">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="c2cf7-132">Pero el código siguiente también es válido, porque garantiza que el control del programa no puede pasar explícitamente a la sección switch `default`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-132">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>
  
 <span data-ttu-id="c2cf7-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-133">[!code-cs[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]</span></span>    
  
 <span data-ttu-id="c2cf7-134">La ejecución de la lista de instrucciones en la sección switch con una etiqueta case que coincide con la expresión de coincidencia comienza con la primera instrucción y continúa a lo largo de la lista de instrucciones, normalmente hasta que se alcanza una instrucción de salto, como `break`, `goto case`, `goto label`, `return` o `throw`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-134">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="c2cf7-135">En este punto, el control se transfiere fuera de la instrucción `switch` o a otra etiqueta case.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-135">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="c2cf7-136">Una instrucción `goto`, si se usa, debe transferir el control a una etiqueta de constante.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-136">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="c2cf7-137">Esta restricción es necesaria, ya que el intento de transferir el control a una etiqueta que no es de constante puede tener efectos secundarios no deseados, como la transferencia de control a una ubicación no deseada en el código o la creación de un bucle sin fin.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-137">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="c2cf7-138">Etiquetas case</span><span class="sxs-lookup"><span data-stu-id="c2cf7-138">Case labels</span></span>

 <span data-ttu-id="c2cf7-139">Cada etiqueta case especifica un patrón que se compara con la expresión de coincidencia (la variable `caseSwitch` en los ejemplos anteriores).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-139">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="c2cf7-140">Si coinciden, el control se transfiere a la sección switch que contiene la **primera** etiqueta case coincidente.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-140">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="c2cf7-141">Si ningún patrón de la etiqueta case coincide con la expresión de coincidencia, el control se transfiere a la sección con la etiqueta case `default`, si la hubiera.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-141">If no case label pattern matches the match expression, control is transfered to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="c2cf7-142">Si no hay ninguna etiqueta case `default`, no se ejecuta ninguna instrucción de ninguna sección switch y el control se transfiere fuera de la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-142">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

 <span data-ttu-id="c2cf7-143">Para más información sobre la instrucción `switch` y la coincidencia de patrones, vea la sección [Coincidencia de patrones con la instrucción `switch`](#pattern).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-143">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

 <span data-ttu-id="c2cf7-144">Dado que C# 6 solo admite el patrón constante y no permite la repetición de valores constantes, las etiquetas case definen valores mutuamente exclusivos y solo un patrón puede coincidir con la expresión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-144">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="c2cf7-145">Por este motivo, el orden en que aparezcan las instrucciones `case` no tiene importancia.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-145">As a result, the order in which `case` statements appear is unimportant.</span></span>

 <span data-ttu-id="c2cf7-146">Pero en C# 7, dado que se admiten otros patrones, las etiquetas case no necesitan definir valores mutuamente exclusivos y varios patrones pueden coincidir con la expresión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-146">In C# 7, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="c2cf7-147">Puesto que solo se ejecutan las instrucciones de la sección switch que contiene el primer patrón coincidente, el orden en que aparecen las instrucciones `case` sí es importante.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-147">Because only the statements in the switch section that contains the first matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="c2cf7-148">Si C# detecta una sección switch cuya instrucción o instrucciones case son equivalentes a o son subconjuntos de instrucciones anteriores, genera un error del compilador, CS8120: "El caso del modificador ya se ha gestionado en un caso anterior".</span><span class="sxs-lookup"><span data-stu-id="c2cf7-148">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span> 

 <span data-ttu-id="c2cf7-149">En el ejemplo siguiente se muestra una instrucción `switch` que usa una variedad de patrones que no son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-149">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="c2cf7-150">Si mueve la sección switch `case 0:` de modo que ya no sea la primera sección de la instrucción `switch`, C# genera un error del compilador debido a que un entero cuyo valor es cero es un subconjunto de todos los enteros, que es el patrón definido por la instrucción `case int val`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-150">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

 <span data-ttu-id="c2cf7-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-151">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]</span></span>    

<span data-ttu-id="c2cf7-152">Puede corregir este problema y eliminar la advertencia del compilador de alguna de estas dos formas:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-152">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="c2cf7-153">Si cambia el orden de las secciones switch.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-153">By changing the order of the switch sections.</span></span> 
 
- <span data-ttu-id="c2cf7-154">Si usa una </a name="when">cláusula when</a> en la etiqueta `case`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-154">By using a </a name="when">when clause</a> in the `case` label.</span></span>
 
## <a name="the-default-case"></a><span data-ttu-id="c2cf7-155">Etiqueta case `default`</span><span class="sxs-lookup"><span data-stu-id="c2cf7-155">The `default` case</span></span>

<span data-ttu-id="c2cf7-156">La etiqueta case `default` especifica la sección switch que se va a ejecutar si la expresión de coincidencia no coincide con ninguna otra etiqueta `case`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-156">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="c2cf7-157">Si no hay ninguna etiqueta case `default` y la expresión de coincidencia no coincide con ninguna otra etiqueta `case`, el flujo del programa pasa a la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-157">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="c2cf7-158">La etiqueta case `default` puede aparecer en cualquier orden en la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-158">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="c2cf7-159">Independientemente de su orden en el código fuente, siempre se evalúa en último lugar, después de que se hayan evaluado las demás etiquetas `case`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-159">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="c2cf7-160"><a name="pattern" /> Coincidencia de patrones con la instrucción `switch`</span><span class="sxs-lookup"><span data-stu-id="c2cf7-160"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>
  
<span data-ttu-id="c2cf7-161">Cada instrucción `case` define un patrón que, si coincide con la expresión de coincidencia, provoca la ejecución de su sección switch contenedora.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-161">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="c2cf7-162">Todas las versiones de C# admiten el patrón de constante.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-162">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="c2cf7-163">Los demás patrones se admiten a partir de C# 7.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-163">The remaining patterns are supported beginning with C# 7.</span></span> 
  
### <a name="constant-pattern"></a><span data-ttu-id="c2cf7-164">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="c2cf7-164">Constant pattern</span></span> 

<span data-ttu-id="c2cf7-165">El patrón de constante comprueba si la expresión de coincidencia es igual a una constante especificada.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-165">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="c2cf7-166">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-166">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="c2cf7-167">donde *constant* es el valor que se va a comprobar.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-167">where *constant* is the value to test for.</span></span> <span data-ttu-id="c2cf7-168">*constant* puede ser cualquiera de las expresiones de constante siguientes:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-168">*constant* can be any of the following constant expressions:</span></span> 

- <span data-ttu-id="c2cf7-169">Un literal [booleano](bool.md), ya sea `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-169">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="c2cf7-170">Cualquier constante entera, como [int](int.md), [long](long.md) o [byte](byte.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-170">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span> 
- <span data-ttu-id="c2cf7-171">El nombre de una variable `const` declarada.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-171">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="c2cf7-172">Una constante de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-172">An enumeration constant.</span></span>
- <span data-ttu-id="c2cf7-173">Un literal de [carácter](char.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-173">A [char](char.md) literal.</span></span>
- <span data-ttu-id="c2cf7-174">Un literal de [cadena](string.md).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-174">A [string](string.md) literal.</span></span>

<span data-ttu-id="c2cf7-175">La expresión de constante se evalúa de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-175">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="c2cf7-176">Si *expr* y *constant* son tipos enteros, el operador de igualdad de C# determina si la expresión devuelve `true` (es decir, si `expr == constant`).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-176">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="c2cf7-177">De lo contrario, el valor de la expresión se determina mediante una llamada al método estático [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)).</span><span class="sxs-lookup"><span data-stu-id="c2cf7-177">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>  

<span data-ttu-id="c2cf7-178">En el ejemplo siguiente se usa el patrón de constante para determinar si una fecha determinada es un fin de semana, el primer día, el último día o la mitad de la semana laboral.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-178">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="c2cf7-179">Evalúa la propiedad [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) del día actual con los miembros de la enumeración @System.DayOfWeek.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-179">It evaluates the [DateTime.DayOfWeek](xref:System.DateTime.DayOfWeek) property of the current day against the members of the @System.DayOfWeek enumeration.</span></span> 

<span data-ttu-id="c2cf7-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-180">[!code-cs[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]</span></span>

<span data-ttu-id="c2cf7-181">En el ejemplo siguiente se usa el patrón de constante para controlar la entrada del usuario en una aplicación de consola que simula una cafetera automática.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-181">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>
  
 <span data-ttu-id="c2cf7-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-182">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]</span></span>  

### <a name="type-pattern"></a><span data-ttu-id="c2cf7-183">Patrón de tipo</span><span class="sxs-lookup"><span data-stu-id="c2cf7-183">Type pattern</span></span>

<span data-ttu-id="c2cf7-184">El patrón de tipo habilita la conversión y la evaluación de tipo concisas.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-184">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="c2cf7-185">Cuando se usa con la instrucción `switch` para realizar la coincidencia de patrones, comprueba si una expresión se puede convertir en un tipo especificado y, en caso afirmativo, la convierte en una variable de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-185">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="c2cf7-186">Su sintaxis es:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-186">Its syntax is:</span></span>

```csharp
   case type varname 
```
<span data-ttu-id="c2cf7-187">donde *type* es el nombre del tipo al que se va a convertir el resultado de *expr* y *varname* es el objeto al que se va a convertir el resultado de *expr* si hay coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-187">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span> 

<span data-ttu-id="c2cf7-188">La expresión `case` es `true` si se cumple alguna de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-188">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="c2cf7-189">*expr* es una instancia del mismo tipo que *type*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-189">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c2cf7-190">*expr* es una instancia de un tipo que deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-190">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c2cf7-191">En otras palabras, el resultado de *expr* puede convertirse en una instancia de *type*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-191">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c2cf7-192">*expr* tiene un tipo en tiempo de compilación que es una clase base de *type* y *expr* tiene un tipo en tiempo de ejecución que es *type* o se deriva de *type*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-192">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c2cf7-193">El *tipo en tiempo de compilación* de una variable es el tipo de la variable tal como se define en su declaración de tipos.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-193">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="c2cf7-194">El *tipo en tiempo de ejecución* de una variable es el tipo de la instancia que se asigna a esa variable.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-194">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c2cf7-195">*type* es una instancia de un tipo que implementa la interfaz *type*.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-195">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c2cf7-196">Si la expresión case es true, *varname* se asigna definitivamente y tiene ámbito local únicamente dentro de la sección switch.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-196">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="c2cf7-197">Tenga en cuenta que `null` no coincide con un tipo.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-197">Note that `null` does not match a type.</span></span> <span data-ttu-id="c2cf7-198">Para que `null` coincida, use la siguiente etiqueta `case`:</span><span class="sxs-lookup"><span data-stu-id="c2cf7-198">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```
 
<span data-ttu-id="c2cf7-199">En el ejemplo siguiente se usa el patrón de tipo para proporcionar información sobre los distintos tipos de colección.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-199">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

<span data-ttu-id="c2cf7-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-200">[!code-cs[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]</span></span>

<span data-ttu-id="c2cf7-201">Sin coincidencia de patrones, este código podría escribirse del modo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-201">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="c2cf7-202">El uso de la coincidencia de patrones de tipo genera código más compacto y legible al eliminar la necesidad de comprobar si el resultado de una conversión es `null` o de realizar conversiones repetidas.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-202">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>  

<span data-ttu-id="c2cf7-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-203">[!code-cs[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]</span></span>

## <a name="the-case-statement-and-the-when-clause"></a><span data-ttu-id="c2cf7-204">Instrucción `case` y cláusula `when`</span><span class="sxs-lookup"><span data-stu-id="c2cf7-204">The `case` statement and the `when` clause</span></span>

<span data-ttu-id="c2cf7-205">A partir de C# 7, dado que las instrucciones case no necesitan ser mutuamente excluyentes, puede agregar una cláusula `when` para especificar una condición adicional que deba cumplirse para que la instrucción case se evalúe como true.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-205">Starting with C# 7, because case statements need not be mutually exclusive, you can use add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="c2cf7-206">La cláusula `when` puede ser cualquier expresión que devuelva un valor booleano.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-206">The `when` clause can be any expression that returns a Boolean value.</span></span> <span data-ttu-id="c2cf7-207">Uno de los usos más comunes de la cláusula `when` es evitar que una sección switch se ejecute cuando el valor de una expresión de coincidencia sea `null`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-207">One of the more common uses for the `when` clause is used to prevent a switch section from executing when the value of a match expression is `null`.</span></span> 

 <span data-ttu-id="c2cf7-208">En el ejemplo siguiente se define una clase base `Shape`, una clase `Rectangle` que deriva de `Shape` y una clase `Square` que deriva de `Rectangle`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-208">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="c2cf7-209">Usa la cláusula `when` para asegurarse de que `ShowShapeInfo` trate a un objeto `Rectangle` al que se han asignado las mismas longitudes y anchos como si fuera `Square` aunque de él no se hayan creado instancias como de un objeto `Square`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-209">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if is has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="c2cf7-210">El método no intenta mostrar información sobre un objeto que es `null` ni sobre una forma cuya área es cero.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-210">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span> 

<span data-ttu-id="c2cf7-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c2cf7-211">[!code-cs[switch#8](../../../../samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]</span></span>
  
<span data-ttu-id="c2cf7-212">Tenga en cuenta que la cláusula `when` del ejemplo que intenta comprobar si un objeto `Shape` es `null` no se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-212">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="c2cf7-213">El patrón de tipo correcto para comprobar `null` es `case null:`.</span><span class="sxs-lookup"><span data-stu-id="c2cf7-213">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c2cf7-214">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c2cf7-214">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2cf7-215">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2cf7-215">See Also</span></span>  

 <span data-ttu-id="c2cf7-216">[Referencia de C#](../index.md) </span><span class="sxs-lookup"><span data-stu-id="c2cf7-216">[C# Reference](../index.md) </span></span>  
 <span data-ttu-id="c2cf7-217">[Guía de programación de C#](../../programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c2cf7-217">[C# Programming Guide](../../programming-guide/index.md) </span></span>  
 <span data-ttu-id="c2cf7-218">[Palabras clave de C#](index.md) </span><span class="sxs-lookup"><span data-stu-id="c2cf7-218">[C# Keywords](index.md) </span></span>  
 <span data-ttu-id="c2cf7-219">[if-else](if-else.md) </span><span class="sxs-lookup"><span data-stu-id="c2cf7-219">[if-else](if-else.md) </span></span>  
 [<span data-ttu-id="c2cf7-220">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="c2cf7-220">Pattern Matching</span></span>](../../pattern-matching.md)   
 

 

