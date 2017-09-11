---
title: "Convenciones de código de C# (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
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
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="f6432-102">Convenciones de código de C# (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f6432-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="f6432-103">La [especificación del lenguaje C#](http://go.microsoft.com/fwlink/?LinkId=199552) no define un estándar de codificación.</span><span class="sxs-lookup"><span data-stu-id="f6432-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="f6432-104">Sin embargo, Microsoft utiliza las instrucciones de este tema para desarrollar ejemplos y documentación.</span><span class="sxs-lookup"><span data-stu-id="f6432-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="f6432-105">Las convenciones de codificación tienen los objetivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6432-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="f6432-106">Crean una apariencia coherente en el código, para que los lectores puedan centrarse en el contenido, no en el diseño.</span><span class="sxs-lookup"><span data-stu-id="f6432-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="f6432-107">Permiten a los lectores comprender el código más rápidamente al hacer suposiciones basadas en la experiencia anterior.</span><span class="sxs-lookup"><span data-stu-id="f6432-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="f6432-108">Facilitan la copia, el cambio y el mantenimiento del código.</span><span class="sxs-lookup"><span data-stu-id="f6432-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="f6432-109">Muestran los procedimientos recomendados de C#.</span><span class="sxs-lookup"><span data-stu-id="f6432-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="f6432-110">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="f6432-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="f6432-111">En ejemplos breves que no incluyen [directivas using](../../../csharp/language-reference/keywords/using-directive.md), use calificaciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f6432-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="f6432-112">Si sabe que un espacio de nombres se importa en un proyecto de forma predeterminada, no es necesario completar los nombres de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f6432-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="f6432-113">Los nombres completos pueden partirse después de un punto (.) si son demasiado largos para una sola línea, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6432-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f6432-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-115">No es necesario cambiar los nombres de objetos que se crearon con las herramientas del diseñador de Visual Studio para que se ajusten a otras directrices.</span><span class="sxs-lookup"><span data-stu-id="f6432-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="f6432-116">Convenciones de diseño</span><span class="sxs-lookup"><span data-stu-id="f6432-116">Layout Conventions</span></span>  
 <span data-ttu-id="f6432-117">Un buen diseño utiliza un formato que destaque la estructura del código y haga que el código sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="f6432-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="f6432-118">Las muestras y ejemplos de Microsoft cumplen las convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6432-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="f6432-119">Utilice la configuración del Editor de código predeterminada (sangría automática, sangrías de 4 caracteres, tabulaciones guardadas como espacios).</span><span class="sxs-lookup"><span data-stu-id="f6432-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="f6432-120">Para obtener más información, vea [Opciones, editor de texto, C#, formato](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="f6432-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="f6432-121">Escriba solo una instrucción por línea.</span><span class="sxs-lookup"><span data-stu-id="f6432-121">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="f6432-122">Escriba solo una declaración por línea.</span><span class="sxs-lookup"><span data-stu-id="f6432-122">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="f6432-123">Si a las líneas de continuación no se les aplica sangría automáticamente, hágalo con una tabulación (cuatro espacios).</span><span class="sxs-lookup"><span data-stu-id="f6432-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="f6432-124">Agregue al menos una línea en blanco entre las definiciones de método y las de propiedad.</span><span class="sxs-lookup"><span data-stu-id="f6432-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="f6432-125">Utilice paréntesis para que las cláusulas de una expresión sean evidentes, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6432-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     <span data-ttu-id="f6432-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="f6432-127">Convenciones de los comentarios</span><span class="sxs-lookup"><span data-stu-id="f6432-127">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="f6432-128">Coloque el comentario en una línea independiente, no al final de una línea de código.</span><span class="sxs-lookup"><span data-stu-id="f6432-128">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="f6432-129">Comience el texto del comentario con una letra mayúscula.</span><span class="sxs-lookup"><span data-stu-id="f6432-129">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="f6432-130">Finalice el texto del comentario con un punto.</span><span class="sxs-lookup"><span data-stu-id="f6432-130">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="f6432-131">Inserte un espacio entre el delimitador de comentario (//) y el texto del comentario, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6432-131">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f6432-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-133">No cree bloques con formato de asteriscos alrededor de comentarios.</span><span class="sxs-lookup"><span data-stu-id="f6432-133">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="f6432-134">Convenciones de lenguaje</span><span class="sxs-lookup"><span data-stu-id="f6432-134">Language Guidelines</span></span>  
 <span data-ttu-id="f6432-135">En las secciones siguientes se describen las prácticas que sigue el equipo C# para preparar las muestras y ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="f6432-135">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="f6432-136">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="f6432-136">String Data Type</span></span>  
  
-   <span data-ttu-id="f6432-137">Utilice el operador `+` para concatenar cadenas cortas, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6432-137">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     <span data-ttu-id="f6432-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-139">Para anexar cadenas en bucles, especialmente cuando se trabaja con grandes cantidades de texto, utilice un objeto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="f6432-139">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="f6432-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span></span>  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="f6432-141">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="f6432-141">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="f6432-142">Use [tipos implícitos](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) para las variables locales cuando el tipo de la variable sea obvio desde el lado derecho de la asignación, o cuando el tipo exacto no sea importante.</span><span class="sxs-lookup"><span data-stu-id="f6432-142">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     <span data-ttu-id="f6432-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-144">No use [var](../../../csharp/language-reference/keywords/var.md) cuando el tipo no sea evidente desde el lado derecho de la asignación.</span><span class="sxs-lookup"><span data-stu-id="f6432-144">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     <span data-ttu-id="f6432-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-146">No confíe en el nombre de variable para especificar el tipo de la variable.</span><span class="sxs-lookup"><span data-stu-id="f6432-146">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="f6432-147">Puede no ser correcto.</span><span class="sxs-lookup"><span data-stu-id="f6432-147">It might not be correct.</span></span>  
  
     <span data-ttu-id="f6432-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-149">Evite el uso de `var` en lugar de [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="f6432-149">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="f6432-150">Use tipos implícitos para determinar el tipo de la variable de bucle en bucles [for](../../../csharp/language-reference/keywords/for.md) y [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="f6432-150">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="f6432-151">En el ejemplo siguiente se usan tipos implícitos en una instrucción `for`.</span><span class="sxs-lookup"><span data-stu-id="f6432-151">The following example uses implicit typing in a `for` statement.</span></span>  
  
     <span data-ttu-id="f6432-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span></span>  
  
     <span data-ttu-id="f6432-153">En el ejemplo siguiente se usan tipos implícitos en una instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="f6432-153">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     <span data-ttu-id="f6432-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="f6432-155">Tipo de datos sin signo</span><span class="sxs-lookup"><span data-stu-id="f6432-155">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="f6432-156">En general, utilice `int` en lugar de tipos sin signo.</span><span class="sxs-lookup"><span data-stu-id="f6432-156">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="f6432-157">El uso de `int` es común en todo C#, y es más fácil interactuar con otras bibliotecas cuando se usa `int`.</span><span class="sxs-lookup"><span data-stu-id="f6432-157">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="f6432-158">Matrices</span><span class="sxs-lookup"><span data-stu-id="f6432-158">Arrays</span></span>  
  
-   <span data-ttu-id="f6432-159">Utilice sintaxis concisa para inicializar las matrices en la línea de declaración.</span><span class="sxs-lookup"><span data-stu-id="f6432-159">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     <span data-ttu-id="f6432-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span></span>  
  
### <a name="delegates"></a><span data-ttu-id="f6432-161">Delegados</span><span class="sxs-lookup"><span data-stu-id="f6432-161">Delegates</span></span>  
  
-   <span data-ttu-id="f6432-162">Utilice sintaxis concisa para crear instancias de un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="f6432-162">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     <span data-ttu-id="f6432-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span></span>  
  
     <span data-ttu-id="f6432-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span></span>  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="f6432-165">Instrucciones try-catch y using en el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="f6432-165">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="f6432-166">Use una instrucción [try-catch](../../../csharp/language-reference/keywords/try-catch.md) en la mayoría de casos de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="f6432-166">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     <span data-ttu-id="f6432-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-168">Simplifique el código mediante la [instrucción using](../../../csharp/language-reference/keywords/using-statement.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="f6432-168">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="f6432-169">Si tiene una instrucción [try-finally](../../../csharp/language-reference/keywords/try-finally.md) en la que el único código del bloque `finally` es una llamada al método <xref:System.IDisposable.Dispose%2A>, use en su lugar una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="f6432-169">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     <span data-ttu-id="f6432-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span></span>  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="f6432-171">Operadores && y &#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="f6432-171">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="f6432-172">Para evitar excepciones y aumentar el rendimiento omitiendo las comparaciones innecesarias, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) en lugar de [&](../../../csharp/language-reference/operators/and-operator.md) y [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) en lugar de [&#124;](../../../csharp/language-reference/operators/or-operator.md) cuando realice comparaciones, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f6432-172">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f6432-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span></span>  
  
### <a name="new-operator"></a><span data-ttu-id="f6432-174">New (Operador)</span><span class="sxs-lookup"><span data-stu-id="f6432-174">New Operator</span></span>  
  
-   <span data-ttu-id="f6432-175">Utilice la forma concisa de la creación de instancias de objeto con tipos implícitos, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="f6432-175">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     <span data-ttu-id="f6432-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span></span>  
  
     <span data-ttu-id="f6432-177">La línea anterior es equivalente a la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="f6432-177">The previous line is equivalent to the following declaration.</span></span>  
  
     <span data-ttu-id="f6432-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-179">Utilice inicializadores de objeto para simplificar la creación de objetos.</span><span class="sxs-lookup"><span data-stu-id="f6432-179">Use object initializers to simplify object creation.</span></span>  
  
     <span data-ttu-id="f6432-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="f6432-181">Control de eventos</span><span class="sxs-lookup"><span data-stu-id="f6432-181">Event Handling</span></span>  
  
-   <span data-ttu-id="f6432-182">Si va a definir un controlador de eventos que no es necesario quitar más tarde, utilice una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="f6432-182">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     <span data-ttu-id="f6432-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span></span>  
  
     <span data-ttu-id="f6432-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span></span>  
  
### <a name="static-members"></a><span data-ttu-id="f6432-185">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="f6432-185">Static Members</span></span>  
  
-   <span data-ttu-id="f6432-186">Llame a miembros [estáticos](../../../csharp/language-reference/keywords/static.md) con el nombre de clase *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="f6432-186">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="f6432-187">Esta práctica hace que el código sea más legible al clarificar el acceso estático.</span><span class="sxs-lookup"><span data-stu-id="f6432-187">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="f6432-188">No califique un miembro estático definido en una clase base con el nombre de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f6432-188">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="f6432-189">Mientras el código se compila, su legibilidad se presta a confusión, y puede interrumpirse en el futuro si se agrega a un miembro estático con el mismo nombre a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="f6432-189">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="f6432-190">Consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="f6432-190">LINQ Queries</span></span>  
  
-   <span data-ttu-id="f6432-191">Utilice nombres descriptivos para las variables de consulta.</span><span class="sxs-lookup"><span data-stu-id="f6432-191">Use meaningful names for query variables.</span></span> <span data-ttu-id="f6432-192">En el ejemplo siguiente, se utiliza `seattleCustomers` para los clientes que se encuentran en Seattle.</span><span class="sxs-lookup"><span data-stu-id="f6432-192">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     <span data-ttu-id="f6432-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-194">Utilice alias para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula o minúscula, usando para ello la grafía Pascal.</span><span class="sxs-lookup"><span data-stu-id="f6432-194">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     <span data-ttu-id="f6432-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-196">Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="f6432-196">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="f6432-197">Por ejemplo, si la consulta devuelve un nombre de cliente y un identificador de distribuidor, en lugar de dejarlos como `Name` e `ID` en el resultado, cambie su nombre para aclarar que `Name` es el nombre de un cliente e `ID` es el identificador de un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="f6432-197">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     <span data-ttu-id="f6432-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-199">Utilice tipos implícitos en la declaración de variables de consulta y variables de intervalo.</span><span class="sxs-lookup"><span data-stu-id="f6432-199">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     <span data-ttu-id="f6432-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-201">Alinee las cláusulas de consulta bajo la cláusula [from](../../../csharp/language-reference/keywords/from-clause.md), como se muestra en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="f6432-201">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="f6432-202">Use cláusulas [where](../../../csharp/language-reference/keywords/where-clause.md) antes de otras cláusulas de consulta para asegurarse de que las cláusulas de consulta posteriores operan en un conjunto de datos reducido y filtrado.</span><span class="sxs-lookup"><span data-stu-id="f6432-202">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     <span data-ttu-id="f6432-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span></span>  
  
-   <span data-ttu-id="f6432-204">Use varias cláusulas `from` en lugar de una cláusula [join](../../../csharp/language-reference/keywords/join-clause.md) para obtener acceso a colecciones internas.</span><span class="sxs-lookup"><span data-stu-id="f6432-204">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="f6432-205">Por ejemplo, una colección de objetos `Student` podría contener cada uno un conjunto de resultados de exámenes.</span><span class="sxs-lookup"><span data-stu-id="f6432-205">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="f6432-206">Cuando se ejecuta la siguiente consulta, devuelve cada resultado superior a 90, además del apellido del alumno que recibió la puntuación.</span><span class="sxs-lookup"><span data-stu-id="f6432-206">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     <span data-ttu-id="f6432-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span><span class="sxs-lookup"><span data-stu-id="f6432-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="f6432-208">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f6432-208">Security</span></span>  
 <span data-ttu-id="f6432-209">Siga las instrucciones de [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="f6432-209">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6432-210">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6432-210">See Also</span></span>  
 <span data-ttu-id="f6432-211">[Convenciones de código de Visual Basic](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f6432-211">[Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span></span>  
 [<span data-ttu-id="f6432-212">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="f6432-212">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

