---
title: 'Convenciones de código de C#: Guía de programación de C#'
description: Aprenda sobre las convenciones de código en C#. Las convenciones de código crean una apariencia coherente del código y facilitan la copia, la modificación y el mantenimiento del código.
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
ms.openlocfilehash: 772aebff0b8c7aebe7c7d5c7634cd2931f4570b1
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301858"
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="17e40-104">Convenciones de código de C# (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="17e40-104">C# Coding Conventions (C# Programming Guide)</span></span>

<span data-ttu-id="17e40-105">Las convenciones de codificación tienen los objetivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e40-105">Coding conventions serve the following purposes:</span></span>  
  
- <span data-ttu-id="17e40-106">Crean una apariencia coherente en el código, para que los lectores puedan centrarse en el contenido, no en el diseño.</span><span class="sxs-lookup"><span data-stu-id="17e40-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
- <span data-ttu-id="17e40-107">Permiten a los lectores comprender el código más rápidamente al hacer suposiciones basadas en la experiencia anterior.</span><span class="sxs-lookup"><span data-stu-id="17e40-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
- <span data-ttu-id="17e40-108">Facilitan la copia, el cambio y el mantenimiento del código.</span><span class="sxs-lookup"><span data-stu-id="17e40-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
- <span data-ttu-id="17e40-109">Muestran los procedimientos recomendados de C#.</span><span class="sxs-lookup"><span data-stu-id="17e40-109">They demonstrate C# best practices.</span></span>  

<span data-ttu-id="17e40-110">Microsoft usa las instrucciones de este artículo para desarrollar ejemplos y documentación.</span><span class="sxs-lookup"><span data-stu-id="17e40-110">The guidelines in this article are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="17e40-111">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="17e40-111">Naming Conventions</span></span>  
  
- <span data-ttu-id="17e40-112">En ejemplos breves que no incluyen [directivas using](../../language-reference/keywords/using-directive.md), use calificaciones de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="17e40-112">In short examples that do not include [using directives](../../language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="17e40-113">Si sabe que un espacio de nombres se importa en un proyecto de forma predeterminada, no es necesario completar los nombres de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="17e40-113">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="17e40-114">Los nombres completos pueden partirse después de un punto (.) si son demasiado largos para una sola línea, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e40-114">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
- <span data-ttu-id="17e40-115">No es necesario cambiar los nombres de objetos que se crearon con las herramientas del diseñador de Visual Studio para que se ajusten a otras directrices.</span><span class="sxs-lookup"><span data-stu-id="17e40-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="17e40-116">Convenciones de diseño</span><span class="sxs-lookup"><span data-stu-id="17e40-116">Layout Conventions</span></span>  

<span data-ttu-id="17e40-117">Un buen diseño utiliza un formato que destaque la estructura del código y haga que el código sea más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="17e40-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="17e40-118">Las muestras y ejemplos de Microsoft cumplen las convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="17e40-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
- <span data-ttu-id="17e40-119">Utilice la configuración del Editor de código predeterminada (sangría automática, sangrías de 4 caracteres, tabulaciones guardadas como espacios).</span><span class="sxs-lookup"><span data-stu-id="17e40-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="17e40-120">Para obtener más información, vea [Opciones, editor de texto, C#, formato](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span><span class="sxs-lookup"><span data-stu-id="17e40-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
- <span data-ttu-id="17e40-121">Escriba solo una instrucción por línea.</span><span class="sxs-lookup"><span data-stu-id="17e40-121">Write only one statement per line.</span></span>  
  
- <span data-ttu-id="17e40-122">Escriba solo una declaración por línea.</span><span class="sxs-lookup"><span data-stu-id="17e40-122">Write only one declaration per line.</span></span>  
  
- <span data-ttu-id="17e40-123">Si a las líneas de continuación no se les aplica sangría automáticamente, hágalo con una tabulación (cuatro espacios).</span><span class="sxs-lookup"><span data-stu-id="17e40-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
- <span data-ttu-id="17e40-124">Agregue al menos una línea en blanco entre las definiciones de método y las de propiedad.</span><span class="sxs-lookup"><span data-stu-id="17e40-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
- <span data-ttu-id="17e40-125">Utilice paréntesis para que las cláusulas de una expresión sean evidentes, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e40-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="17e40-126">Convenciones de los comentarios</span><span class="sxs-lookup"><span data-stu-id="17e40-126">Commenting Conventions</span></span>  
  
- <span data-ttu-id="17e40-127">Coloque el comentario en una línea independiente, no al final de una línea de código.</span><span class="sxs-lookup"><span data-stu-id="17e40-127">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
- <span data-ttu-id="17e40-128">Comience el texto del comentario con una letra mayúscula.</span><span class="sxs-lookup"><span data-stu-id="17e40-128">Begin comment text with an uppercase letter.</span></span>  
  
- <span data-ttu-id="17e40-129">Finalice el texto del comentario con un punto.</span><span class="sxs-lookup"><span data-stu-id="17e40-129">End comment text with a period.</span></span>  
  
- <span data-ttu-id="17e40-130">Inserte un espacio entre el delimitador de comentario (//) y el texto del comentario, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e40-130">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
- <span data-ttu-id="17e40-131">No cree bloques con formato de asteriscos alrededor de comentarios.</span><span class="sxs-lookup"><span data-stu-id="17e40-131">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="17e40-132">Convenciones de lenguaje</span><span class="sxs-lookup"><span data-stu-id="17e40-132">Language Guidelines</span></span>  

<span data-ttu-id="17e40-133">En las secciones siguientes se describen las prácticas que sigue el equipo C# para preparar las muestras y ejemplos de código.</span><span class="sxs-lookup"><span data-stu-id="17e40-133">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="17e40-134">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="17e40-134">String Data Type</span></span>  
  
- <span data-ttu-id="17e40-135">Use [interpolación de cadenas](../../language-reference/tokens/interpolated.md) para concatenar cadenas cortas, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e40-135">Use [string interpolation](../../language-reference/tokens/interpolated.md) to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
- <span data-ttu-id="17e40-136">Para anexar cadenas en bucles, especialmente cuando se trabaja con grandes cantidades de texto, utilice un objeto <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="17e40-136">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="17e40-137">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="17e40-137">Implicitly Typed Local Variables</span></span>  
  
- <span data-ttu-id="17e40-138">Use [tipos implícitos](../classes-and-structs/implicitly-typed-local-variables.md) para las variables locales cuando el tipo de la variable sea obvio desde el lado derecho de la asignación, o cuando el tipo exacto no sea importante.</span><span class="sxs-lookup"><span data-stu-id="17e40-138">Use [implicit typing](../classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
- <span data-ttu-id="17e40-139">No use [var](../../language-reference/keywords/var.md) cuando el tipo no sea evidente desde el lado derecho de la asignación.</span><span class="sxs-lookup"><span data-stu-id="17e40-139">Do not use [var](../../language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
- <span data-ttu-id="17e40-140">No confíe en el nombre de variable para especificar el tipo de la variable.</span><span class="sxs-lookup"><span data-stu-id="17e40-140">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="17e40-141">Puede no ser correcto.</span><span class="sxs-lookup"><span data-stu-id="17e40-141">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
- <span data-ttu-id="17e40-142">Evite el uso de `var` en lugar de [dynamic](../../language-reference/builtin-types/reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="17e40-142">Avoid the use of `var` in place of [dynamic](../../language-reference/builtin-types/reference-types.md).</span></span>  
  
- <span data-ttu-id="17e40-143">Use tipos implícitos para determinar el tipo de la variable de bucle en bucles [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="17e40-143">Use implicit typing to determine the type of the loop variable in [for](../../language-reference/keywords/for.md) loops.</span></span>  
  
     <span data-ttu-id="17e40-144">En el ejemplo siguiente se usan tipos implícitos en una instrucción `for`.</span><span class="sxs-lookup"><span data-stu-id="17e40-144">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  

- <span data-ttu-id="17e40-145">No use tipos implícitos para determinar el tipo de la variable de bucle en bucles [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="17e40-145">Do not use implicit typing to determine the type of the loop variable in [foreach](../../language-reference/keywords/foreach-in.md) loops.</span></span>

     <span data-ttu-id="17e40-146">En el ejemplo siguiente se usan tipos explícitos en una instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="17e40-146">The following example uses explicit typing in a `foreach` statement.</span></span>

     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]

     > [!NOTE]
     > <span data-ttu-id="17e40-147">Tenga cuidado de no cambiar accidentalmente un tipo de elemento de la colección iterable.</span><span class="sxs-lookup"><span data-stu-id="17e40-147">Be careful not to accidentally change a type of an element of the iterable collection.</span></span> <span data-ttu-id="17e40-148">Por ejemplo, es fácil cambiar de <xref:System.Linq.IQueryable?displayProperty=nameWithType> a <xref:System.Collections.IEnumerable?displayProperty=nameWithType> en una instrucción `foreach`, lo cual cambia la ejecución de una consulta.</span><span class="sxs-lookup"><span data-stu-id="17e40-148">For example, it is easy to switch from <xref:System.Linq.IQueryable?displayProperty=nameWithType> to <xref:System.Collections.IEnumerable?displayProperty=nameWithType> in a `foreach` statement, which changes the execution of a query.</span></span>

### <a name="unsigned-data-type"></a><span data-ttu-id="17e40-149">Tipo de datos sin signo</span><span class="sxs-lookup"><span data-stu-id="17e40-149">Unsigned Data Type</span></span>  
  
<span data-ttu-id="17e40-150">En general, utilice `int` en lugar de tipos sin signo.</span><span class="sxs-lookup"><span data-stu-id="17e40-150">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="17e40-151">El uso de `int` es común en todo C#, y es más fácil interactuar con otras bibliotecas cuando se usa `int`.</span><span class="sxs-lookup"><span data-stu-id="17e40-151">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="17e40-152">Matrices</span><span class="sxs-lookup"><span data-stu-id="17e40-152">Arrays</span></span>  
  
<span data-ttu-id="17e40-153">Utilice sintaxis concisa para inicializar las matrices en la línea de declaración.</span><span class="sxs-lookup"><span data-stu-id="17e40-153">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="17e40-154">Delegados</span><span class="sxs-lookup"><span data-stu-id="17e40-154">Delegates</span></span>  
  
<span data-ttu-id="17e40-155">Utilice sintaxis concisa para crear instancias de un tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="17e40-155">Use the concise syntax to create instances of a delegate type.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
[!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="17e40-156">Instrucciones try-catch y using en el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="17e40-156">try-catch and using Statements in Exception Handling</span></span>  
  
- <span data-ttu-id="17e40-157">Use una instrucción [try-catch](../../language-reference/keywords/try-catch.md) en la mayoría de casos de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="17e40-157">Use a [try-catch](../../language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
- <span data-ttu-id="17e40-158">Simplifique el código mediante la [instrucción using](../../language-reference/keywords/using-statement.md) de C#.</span><span class="sxs-lookup"><span data-stu-id="17e40-158">Simplify your code by using the C# [using statement](../../language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="17e40-159">Si tiene una instrucción [try-finally](../../language-reference/keywords/try-finally.md) en la que el único código del bloque `finally` es una llamada al método <xref:System.IDisposable.Dispose%2A>, use en su lugar una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="17e40-159">If you have a [try-finally](../../language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="17e40-160">Operadores && y &#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="17e40-160">&& and &#124;&#124; Operators</span></span>  
  
<span data-ttu-id="17e40-161">Para evitar excepciones y aumentar el rendimiento omitiendo las comparaciones innecesarias, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) en lugar de [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) y [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) en lugar de [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) cuando realice comparaciones, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="17e40-161">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-and-operator-) instead of [&](../../language-reference/operators/boolean-logical-operators.md#logical-and-operator-) and [&#124;&#124;](../../language-reference/operators/boolean-logical-operators.md#conditional-logical-or-operator-) instead of [&#124;](../../language-reference/operators/boolean-logical-operators.md#logical-or-operator-) when you perform comparisons, as shown in the following example.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="17e40-162">New (Operador)</span><span class="sxs-lookup"><span data-stu-id="17e40-162">New Operator</span></span>  
  
- <span data-ttu-id="17e40-163">Utilice la forma concisa de la creación de instancias de objeto con tipos implícitos, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="17e40-163">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="17e40-164">La línea anterior es equivalente a la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="17e40-164">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
- <span data-ttu-id="17e40-165">Utilice inicializadores de objeto para simplificar la creación de objetos.</span><span class="sxs-lookup"><span data-stu-id="17e40-165">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="17e40-166">Control de eventos</span><span class="sxs-lookup"><span data-stu-id="17e40-166">Event Handling</span></span>  
  
<span data-ttu-id="17e40-167">Si va a definir un controlador de eventos que no es necesario quitar más tarde, utilice una expresión lambda.</span><span class="sxs-lookup"><span data-stu-id="17e40-167">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
[!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
[!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="17e40-168">Miembros estáticos</span><span class="sxs-lookup"><span data-stu-id="17e40-168">Static Members</span></span>  
  
<span data-ttu-id="17e40-169">Llame a miembros [estáticos](../../language-reference/keywords/static.md) con el nombre de clase: *ClassName.StaticMember*.</span><span class="sxs-lookup"><span data-stu-id="17e40-169">Call [static](../../language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="17e40-170">Esta práctica hace que el código sea más legible al clarificar el acceso estático.</span><span class="sxs-lookup"><span data-stu-id="17e40-170">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="17e40-171">No califique un miembro estático definido en una clase base con el nombre de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="17e40-171">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="17e40-172">Mientras el código se compila, su legibilidad se presta a confusión, y puede interrumpirse en el futuro si se agrega a un miembro estático con el mismo nombre a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="17e40-172">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="17e40-173">Consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="17e40-173">LINQ Queries</span></span>  
  
- <span data-ttu-id="17e40-174">Utilice nombres descriptivos para las variables de consulta.</span><span class="sxs-lookup"><span data-stu-id="17e40-174">Use meaningful names for query variables.</span></span> <span data-ttu-id="17e40-175">En el ejemplo siguiente, se utiliza `seattleCustomers` para los clientes que se encuentran en Seattle.</span><span class="sxs-lookup"><span data-stu-id="17e40-175">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="17e40-176">Utilice alias para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula o minúscula, usando para ello la grafía Pascal.</span><span class="sxs-lookup"><span data-stu-id="17e40-176">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
- <span data-ttu-id="17e40-177">Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="17e40-177">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="17e40-178">Por ejemplo, si la consulta devuelve un nombre de cliente y un identificador de distribuidor, en lugar de dejarlos como `Name` e `ID` en el resultado, cambie su nombre para aclarar que `Name` es el nombre de un cliente e `ID` es el identificador de un distribuidor.</span><span class="sxs-lookup"><span data-stu-id="17e40-178">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
- <span data-ttu-id="17e40-179">Utilice tipos implícitos en la declaración de variables de consulta y variables de intervalo.</span><span class="sxs-lookup"><span data-stu-id="17e40-179">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
- <span data-ttu-id="17e40-180">Alinee las cláusulas de consulta bajo la cláusula [from](../../language-reference/keywords/from-clause.md), como se muestra en los ejemplos anteriores.</span><span class="sxs-lookup"><span data-stu-id="17e40-180">Align query clauses under the [from](../../language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
- <span data-ttu-id="17e40-181">Use cláusulas [where](../../language-reference/keywords/where-clause.md) antes de otras cláusulas de consulta para asegurarse de que las cláusulas de consulta posteriores operan en un conjunto de datos reducido y filtrado.</span><span class="sxs-lookup"><span data-stu-id="17e40-181">Use [where](../../language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
- <span data-ttu-id="17e40-182">Use varias cláusulas `from` en lugar de una cláusula [join](../../language-reference/keywords/join-clause.md) para obtener acceso a colecciones internas.</span><span class="sxs-lookup"><span data-stu-id="17e40-182">Use multiple `from` clauses instead of a [join](../../language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="17e40-183">Por ejemplo, una colección de objetos `Student` podría contener cada uno un conjunto de resultados de exámenes.</span><span class="sxs-lookup"><span data-stu-id="17e40-183">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="17e40-184">Cuando se ejecuta la siguiente consulta, devuelve cada resultado superior a 90, además del apellido del alumno que recibió la puntuación.</span><span class="sxs-lookup"><span data-stu-id="17e40-184">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="17e40-185">Seguridad</span><span class="sxs-lookup"><span data-stu-id="17e40-185">Security</span></span>  

<span data-ttu-id="17e40-186">Siga las instrucciones de [Instrucciones de codificación segura](../../../standard/security/secure-coding-guidelines.md).</span><span class="sxs-lookup"><span data-stu-id="17e40-186">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e40-187">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17e40-187">See also</span></span>

- [<span data-ttu-id="17e40-188">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="17e40-188">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)
- [<span data-ttu-id="17e40-189">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="17e40-189">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
