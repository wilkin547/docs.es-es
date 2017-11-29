---
title: "Convenciones de código de Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afea862fb8783da3e69fd9828e0ded67fb81b00e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="d8685-102">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d8685-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="d8685-103">Microsoft desarrolla ejemplos y documentación que siga las directrices descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="d8685-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="d8685-104">Si sigue las mismas convenciones de codificación, puede obtener las ventajas siguientes:</span><span class="sxs-lookup"><span data-stu-id="d8685-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="d8685-105">El código tendrá una apariencia coherente, para que los lectores puedan centrarse mejor en el contenido, no en el diseño.</span><span class="sxs-lookup"><span data-stu-id="d8685-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="d8685-106">Los lectores comprender el código más rápidamente porque pueden hacer suposiciones basadas en la experiencia anterior.</span><span class="sxs-lookup"><span data-stu-id="d8685-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="d8685-107">Puede copiar, modificar y mantener más fácilmente el código.</span><span class="sxs-lookup"><span data-stu-id="d8685-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="d8685-108">Para ayudar a asegurarse de que el código muestra "prácticas recomendadas" para Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d8685-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="d8685-109">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="d8685-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="d8685-110">Para obtener información acerca de las directrices de nomenclatura, consulte [directrices de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) tema.</span><span class="sxs-lookup"><span data-stu-id="d8685-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="d8685-111">No utilice "Mi" o "Mi" como parte de un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="d8685-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="d8685-112">Este procedimiento crea confusión con los `My` objetos.</span><span class="sxs-lookup"><span data-stu-id="d8685-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="d8685-113">No es necesario cambiar los nombres de objetos en el código generado automáticamente para que se ajusten a las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="d8685-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="d8685-114">Convenciones de diseño</span><span class="sxs-lookup"><span data-stu-id="d8685-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="d8685-115">Inserte las tabulaciones como espacios y utilice sangrías con una sangría de cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="d8685-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="d8685-116">Use **lista descriptiva (nuevo formato) de código** volver a formatear el código en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="d8685-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="d8685-117">Para obtener más información, consulte [opciones, Editor de texto, básico (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d8685-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="d8685-118">Usar solo una instrucción por línea.</span><span class="sxs-lookup"><span data-stu-id="d8685-118">Use only one statement per line.</span></span> <span data-ttu-id="d8685-119">No use el carácter de separador de línea de Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="d8685-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="d8685-120">Evite usar el carácter de continuación de línea explícita "_" en favor de continuación de línea implícita siempre que sea el lenguaje lo permite.</span><span class="sxs-lookup"><span data-stu-id="d8685-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="d8685-121">Usar solo una declaración por línea.</span><span class="sxs-lookup"><span data-stu-id="d8685-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="d8685-122">Si **lista descriptiva (nuevo formato) de código** no las líneas de continuación de formato automáticamente, manualmente aplicar sangría a continuación líneas una tabulación.</span><span class="sxs-lookup"><span data-stu-id="d8685-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="d8685-123">Sin embargo, siempre Alinear a la izquierda elementos en una lista.</span><span class="sxs-lookup"><span data-stu-id="d8685-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="d8685-124">Agregue al menos una línea en blanco entre las definiciones de método y propiedad.</span><span class="sxs-lookup"><span data-stu-id="d8685-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="d8685-125">Convenciones de los comentarios</span><span class="sxs-lookup"><span data-stu-id="d8685-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="d8685-126">Colocar comentarios en una línea independiente en lugar de al final de una línea de código.</span><span class="sxs-lookup"><span data-stu-id="d8685-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="d8685-127">Inicie el texto del comentario con una letra mayúscula y texto del comentario final con un punto.</span><span class="sxs-lookup"><span data-stu-id="d8685-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="d8685-128">Inserte un espacio entre el delimitador de comentario (') y el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="d8685-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="d8685-129">No se especifica los comentarios con bloques con formato de asteriscos.</span><span class="sxs-lookup"><span data-stu-id="d8685-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="d8685-130">Estructura del programa</span><span class="sxs-lookup"><span data-stu-id="d8685-130">Program Structure</span></span>  
  
-   <span data-ttu-id="d8685-131">Cuando se usa el `Main` método, utilice la construcción predeterminada para las nuevas aplicaciones de consola y usar `My` para los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d8685-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="d8685-132">Convenciones de lenguaje</span><span class="sxs-lookup"><span data-stu-id="d8685-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="d8685-133">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="d8685-133">String Data Type</span></span>  
  
-   <span data-ttu-id="d8685-134">Para concatenar cadenas, utilice una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="d8685-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="d8685-135">Para anexar cadenas en bucles, utilice el <xref:System.Text.StringBuilder> objeto.</span><span class="sxs-lookup"><span data-stu-id="d8685-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="d8685-136">Delegados flexibles en controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="d8685-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="d8685-137">No calificar explícitamente los argumentos (objeto y EventArgs) a controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="d8685-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="d8685-138">Si no utiliza argumentos de evento que se pasan a un evento (por ejemplo, el remitente como Object, e as EventArgs), utilice a delegados flexibles y omita los argumentos del evento en el código:</span><span class="sxs-lookup"><span data-stu-id="d8685-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="d8685-139">Tipo de datos sin signo</span><span class="sxs-lookup"><span data-stu-id="d8685-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="d8685-140">Use `Integer` en lugar de tipos sin signo, excepto cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="d8685-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="d8685-141">Matrices</span><span class="sxs-lookup"><span data-stu-id="d8685-141">Arrays</span></span>  
  
-   <span data-ttu-id="d8685-142">Utilice la sintaxis abreviada al inicializar las matrices en la línea de declaración.</span><span class="sxs-lookup"><span data-stu-id="d8685-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="d8685-143">Por ejemplo, use la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d8685-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="d8685-144">No utilice la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d8685-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="d8685-145">Coloque el designador de matriz en el tipo, no en la variable.</span><span class="sxs-lookup"><span data-stu-id="d8685-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="d8685-146">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8685-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="d8685-147">No use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8685-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="d8685-148">Use la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos.</span><span class="sxs-lookup"><span data-stu-id="d8685-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="d8685-149">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8685-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="d8685-150">No use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8685-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="d8685-151">Use el con la palabra clave</span><span class="sxs-lookup"><span data-stu-id="d8685-151">Use the With Keyword</span></span>  
 <span data-ttu-id="d8685-152">Al realizar una serie de llamadas a un objeto, considere el uso de la `With` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="d8685-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="d8685-153">Utilizar las instrucciones Try... Catch e instrucciones Using cuando se usa el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="d8685-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="d8685-154">No utilice `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="d8685-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="d8685-155">Utilice la palabra clave IsNot</span><span class="sxs-lookup"><span data-stu-id="d8685-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="d8685-156">Use la `IsNot` palabra clave en lugar de `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d8685-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="d8685-157">Nueva palabra clave</span><span class="sxs-lookup"><span data-stu-id="d8685-157">New Keyword</span></span>  
  
-   <span data-ttu-id="d8685-158">Utilice la creación de instancias corta.</span><span class="sxs-lookup"><span data-stu-id="d8685-158">Use short instantiation.</span></span> <span data-ttu-id="d8685-159">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8685-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="d8685-160">La línea anterior es equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="d8685-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="d8685-161">Usar a inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:</span><span class="sxs-lookup"><span data-stu-id="d8685-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="d8685-162">Control de eventos</span><span class="sxs-lookup"><span data-stu-id="d8685-162">Event Handling</span></span>  
  
-   <span data-ttu-id="d8685-163">Use `Handles` en lugar de `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="d8685-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="d8685-164">Use `AddressOf`y no crea una instancia del delegado explícitamente:</span><span class="sxs-lookup"><span data-stu-id="d8685-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="d8685-165">Al definir un evento, use la sintaxis abreviada y dejar que el compilador defina al delegado:</span><span class="sxs-lookup"><span data-stu-id="d8685-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="d8685-166">No comprobar si un evento es `Nothing` (null) antes de llamar a la `RaiseEvent` método.</span><span class="sxs-lookup"><span data-stu-id="d8685-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="d8685-167">`RaiseEvent`busca `Nothing` antes de que genera el evento.</span><span class="sxs-lookup"><span data-stu-id="d8685-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="d8685-168">Utilizar miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="d8685-168">Using Shared Members</span></span>  
 <span data-ttu-id="d8685-169">Llame a `Shared` miembros mediante el nombre de clase, no de una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="d8685-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="d8685-170">Utilizar literales XML</span><span class="sxs-lookup"><span data-stu-id="d8685-170">Use XML Literals</span></span>  
 <span data-ttu-id="d8685-171">Los literales XML simplifican las tareas más comunes que encuentre al trabajar con XML (por ejemplo, carga, consulta y transformación).</span><span class="sxs-lookup"><span data-stu-id="d8685-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="d8685-172">Al desarrollar con XML, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d8685-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="d8685-173">Utilizar literales XML para crear documentos XML y fragmentos en lugar de llamar directamente a las API de XML.</span><span class="sxs-lookup"><span data-stu-id="d8685-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="d8685-174">Importe los espacios de nombres XML en el nivel de archivo o proyecto para aprovechar las ventajas de las optimizaciones de rendimiento para los literales XML.</span><span class="sxs-lookup"><span data-stu-id="d8685-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="d8685-175">Utilice las propiedades de eje XML para tener acceso a elementos y atributos en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="d8685-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="d8685-176">Utilizar expresiones incrustadas para incluir valores y crear XML a partir de los valores existentes en lugar de utilizar llamadas a la API, como el `Add` método:</span><span class="sxs-lookup"><span data-stu-id="d8685-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="d8685-177">Consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="d8685-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="d8685-178">Utilice nombres descriptivos para las variables de consulta:</span><span class="sxs-lookup"><span data-stu-id="d8685-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="d8685-179">Proporcionar nombres para los elementos en una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente con mayúscula utilizando la grafía Pascal de mayúsculas y minúsculas:</span><span class="sxs-lookup"><span data-stu-id="d8685-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="d8685-180">Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="d8685-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="d8685-181">Por ejemplo, si la consulta devuelve un cliente, nombre y un identificador de pedido, cambiar su nombre en lugar de dejarlos como `Name` y `ID` en el resultado:</span><span class="sxs-lookup"><span data-stu-id="d8685-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="d8685-182">Usar la inferencia de tipo en la declaración de variables de consulta y las variables de rango:</span><span class="sxs-lookup"><span data-stu-id="d8685-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="d8685-183">Alinee las cláusulas de consulta en el `From` instrucción:</span><span class="sxs-lookup"><span data-stu-id="d8685-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="d8685-184">Use `Where` cláusulas antes que otras las cláusulas de consulta para que las cláusulas de consulta posteriores operan en el conjunto filtrado de datos:</span><span class="sxs-lookup"><span data-stu-id="d8685-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="d8685-185">Use la `Join` cláusula para definir explícitamente una operación de combinación en lugar de utilizar el `Where` cláusula para definir implícitamente una operación de combinación:</span><span class="sxs-lookup"><span data-stu-id="d8685-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d8685-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8685-186">See Also</span></span>  
 [<span data-ttu-id="d8685-187">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="d8685-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
