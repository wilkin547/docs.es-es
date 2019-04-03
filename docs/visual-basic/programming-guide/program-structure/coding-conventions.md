---
title: Convenciones de código de Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
ms.openlocfilehash: f73648888b28c349104a70e78c29eb208d438b78
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814567"
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="9b9a2-102">Convenciones de código de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9b9a2-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="9b9a2-103">Microsoft desarrolla los ejemplos y documentación que siguen las directrices descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="9b9a2-104">Si sigue las mismas convenciones de codificación, obtendrá las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="9b9a2-105">El código tendrá una apariencia coherente, para que los lectores puedan centrarse mejor en el contenido, no en el diseño.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="9b9a2-106">Los lectores comprender el código más rápidamente ya que pueden hacer suposiciones en función de la experiencia anterior.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="9b9a2-107">Puede copiar, modificar y mantener más fácilmente el código.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="9b9a2-108">Ayudan a garantizar que el código muestra "procedimientos recomendados" de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="9b9a2-109">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="9b9a2-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="9b9a2-110">Para obtener información acerca de las directrices de nomenclatura, consulte [instrucciones de nomenclatura](../../../standard/design-guidelines/naming-guidelines.md) tema.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="9b9a2-111">No utilice "Mi" o "Mi" como parte de un nombre de variable.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="9b9a2-112">Esta práctica crea confusión con los `My` objetos.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="9b9a2-113">No es necesario cambiar los nombres de objetos en el código generado automáticamente para que se ajusten a las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="9b9a2-114">Convenciones de diseño</span><span class="sxs-lookup"><span data-stu-id="9b9a2-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="9b9a2-115">Inserte tabulaciones como espacios y use la sangría inteligente con sangrías de cuatro espacios.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="9b9a2-116">Use **lista descriptiva (nuevo formato) de código** volver a formatear el código en el editor de código.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="9b9a2-117">Para obtener más información, consulte [opciones, Editor de texto, básico (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9b9a2-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="9b9a2-118">Utilice sólo una instrucción por línea.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-118">Use only one statement per line.</span></span> <span data-ttu-id="9b9a2-119">No use el carácter de separador de línea de Visual Basic (:).</span><span class="sxs-lookup"><span data-stu-id="9b9a2-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="9b9a2-120">Evite usar el carácter de continuación de línea explícito "_" en favor de continuación de línea implícita siempre que sea el lenguaje lo permita.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="9b9a2-121">Use solo una declaración por línea.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="9b9a2-122">Si **lista descriptiva (nuevo formato) de código** no formato las líneas de continuación automáticamente, manualmente aplicar sangría a continuación líneas una tabulación.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="9b9a2-123">Sin embargo, siempre Alinear a la izquierda los elementos de una lista.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="9b9a2-124">Agregue al menos una línea en blanco entre definiciones de método y propiedad.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="9b9a2-125">Convenciones de los comentarios</span><span class="sxs-lookup"><span data-stu-id="9b9a2-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="9b9a2-126">Ponga los comentarios en una línea independiente en lugar de al final de una línea de código.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="9b9a2-127">Inicie el texto del comentario con una letra mayúscula y texto del comentario de final con un punto.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="9b9a2-128">Inserte un espacio entre el delimitador de comentario (') y el texto del comentario.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#2)]  
  
-   <span data-ttu-id="9b9a2-129">No especifique comentarios con bloques con formato de asteriscos.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="9b9a2-130">Estructura del programa</span><span class="sxs-lookup"><span data-stu-id="9b9a2-130">Program Structure</span></span>  
  
-   <span data-ttu-id="9b9a2-131">Cuando se usa el `Main` método, utilice la construcción predeterminada para nuevas aplicaciones de consola y usar `My` para los argumentos de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#3)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="9b9a2-132">Convenciones de lenguaje</span><span class="sxs-lookup"><span data-stu-id="9b9a2-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="9b9a2-133">String (Tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="9b9a2-133">String Data Type</span></span>  
  
-   <span data-ttu-id="9b9a2-134">Para concatenar cadenas, utilice una y comercial (&).</span><span class="sxs-lookup"><span data-stu-id="9b9a2-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#4)]  
  
-   <span data-ttu-id="9b9a2-135">Para anexar cadenas en bucles, utilice el <xref:System.Text.StringBuilder> objeto.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#5)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="9b9a2-136">Delegados flexibles en controladores de eventos</span><span class="sxs-lookup"><span data-stu-id="9b9a2-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="9b9a2-137">No califique explícitamente los argumentos (Object y EventArgs) a controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="9b9a2-138">Si no usa los argumentos del evento que se pasan a un evento (por ejemplo, el remitente como objeto como EventArgs), utilice a los delegados flexibles y omita los argumentos del evento en el código:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#7)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="9b9a2-139">Tipo de datos sin signo</span><span class="sxs-lookup"><span data-stu-id="9b9a2-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="9b9a2-140">Use `Integer` en lugar de tipos sin signo, excepto cuando sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="9b9a2-141">Matrices</span><span class="sxs-lookup"><span data-stu-id="9b9a2-141">Arrays</span></span>  
  
-   <span data-ttu-id="9b9a2-142">Utilice la sintaxis abreviada para inicializar las matrices en la línea de declaración.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="9b9a2-143">Por ejemplo, use la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#8)]  
  
     <span data-ttu-id="9b9a2-144">No utilice la siguiente sintaxis.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#9)]  
  
-   <span data-ttu-id="9b9a2-145">Sitúe el designador en el tipo, no en la variable.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="9b9a2-146">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#11)]  
  
     <span data-ttu-id="9b9a2-147">No use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#10)]  
  
-   <span data-ttu-id="9b9a2-148">Utilice la sintaxis {} al declarar e inicializar matrices de tipos de datos básicos.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="9b9a2-149">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#12)]  
  
     <span data-ttu-id="9b9a2-150">No use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#13)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="9b9a2-151">Use la palabra clave</span><span class="sxs-lookup"><span data-stu-id="9b9a2-151">Use the With Keyword</span></span>  
 <span data-ttu-id="9b9a2-152">Al realizar una serie de llamadas a un objeto, considere el uso de la `With` palabra clave:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#15)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="9b9a2-153">Usar Try... Catch y las instrucciones Using al usar el control de excepciones</span><span class="sxs-lookup"><span data-stu-id="9b9a2-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="9b9a2-154">No use `On Error Goto`.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="9b9a2-155">Use la palabra clave IsNot</span><span class="sxs-lookup"><span data-stu-id="9b9a2-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="9b9a2-156">Use la `IsNot` palabra clave en lugar de `Not...Is Nothing`.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="9b9a2-157">Nueva palabra clave</span><span class="sxs-lookup"><span data-stu-id="9b9a2-157">New Keyword</span></span>  
  
-   <span data-ttu-id="9b9a2-158">Utilice la creación de instancias abreviada.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-158">Use short instantiation.</span></span> <span data-ttu-id="9b9a2-159">Por ejemplo, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#21)]  
  
     <span data-ttu-id="9b9a2-160">La línea anterior es equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#22)]  
  
-   <span data-ttu-id="9b9a2-161">Usar a inicializadores de objeto para los nuevos objetos en lugar del constructor sin parámetros:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#23)]  
  
### <a name="event-handling"></a><span data-ttu-id="9b9a2-162">Control de eventos</span><span class="sxs-lookup"><span data-stu-id="9b9a2-162">Event Handling</span></span>  
  
-   <span data-ttu-id="9b9a2-163">Use `Handles` lugar `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#24)]  
  
-   <span data-ttu-id="9b9a2-164">Use `AddressOf`y no crear explícitamente instancias del delegado:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#25)]  
  
-   <span data-ttu-id="9b9a2-165">Al definir un evento, utilice la sintaxis corta y permita que el compilador defina al delegado:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#26)]  
  
-   <span data-ttu-id="9b9a2-166">No comprobar si un evento es `Nothing` (null) antes de llamar a la `RaiseEvent` método.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="9b9a2-167">`RaiseEvent` comprueba si hay `Nothing` antes de que se genera el evento.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="9b9a2-168">Utilizar miembros compartidos</span><span class="sxs-lookup"><span data-stu-id="9b9a2-168">Using Shared Members</span></span>  
 <span data-ttu-id="9b9a2-169">Llamar a `Shared` miembros con el nombre de clase, no una variable de instancia.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="9b9a2-170">Utilice literales XML</span><span class="sxs-lookup"><span data-stu-id="9b9a2-170">Use XML Literals</span></span>  
 <span data-ttu-id="9b9a2-171">Los literales XML simplifican las tareas más comunes que encontrar al trabajar con XML (por ejemplo, carga, consulta y transformación).</span><span class="sxs-lookup"><span data-stu-id="9b9a2-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="9b9a2-172">Al desarrollar con XML, siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="9b9a2-173">Utilice literales XML para crear documentos XML y fragmentos en lugar de llamar directamente a las API de XML.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="9b9a2-174">Importe los espacios de nombres XML en el nivel de archivo o proyecto para aprovechar las ventajas de las optimizaciones de rendimiento para los literales XML.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="9b9a2-175">Utilice las propiedades de eje XML para tener acceso a los elementos y atributos en un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="9b9a2-176">Utilizar expresiones incrustadas para incluir los valores y crear XML de los valores existentes en lugar de utilizar llamadas a la API, como el `Add` método:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#27)]  
  
### <a name="linq-queries"></a><span data-ttu-id="9b9a2-177">Consultas LINQ</span><span class="sxs-lookup"><span data-stu-id="9b9a2-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="9b9a2-178">Utilice nombres descriptivos para las variables de consulta:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#28)]  
  
-   <span data-ttu-id="9b9a2-179">Proporcionar nombres para los elementos de una consulta para asegurarse de que los nombres de propiedad de tipos anónimos se escriben correctamente mediante la grafía Pascal mayúsculas y minúsculas:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#29)]  
  
-   <span data-ttu-id="9b9a2-180">Cambie el nombre de las propiedades cuando puedan ser ambiguos en el resultado.</span><span class="sxs-lookup"><span data-stu-id="9b9a2-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="9b9a2-181">Por ejemplo, si la consulta devuelve un cliente, nombre y un identificador de pedido, cambiar su nombre en lugar de dejarlos como `Name` y `ID` en el resultado:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#30)]  
  
-   <span data-ttu-id="9b9a2-182">Usar la inferencia de tipo en la declaración de variables de consulta y las variables de rango:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#31)]  
  
-   <span data-ttu-id="9b9a2-183">Alinee las cláusulas de consulta bajo la `From` instrucción:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#32)]  
  
-   <span data-ttu-id="9b9a2-184">Use `Where` cláusulas antes que otras cláusulas de consulta para que las cláusulas de consulta posteriores operan en el conjunto filtrado de datos:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#33)]  
  
-   <span data-ttu-id="9b9a2-185">Use la `Join` cláusula para definir explícitamente una operación de combinación en lugar de usar el `Where` cláusula para definir implícitamente una operación de combinación:</span><span class="sxs-lookup"><span data-stu-id="9b9a2-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrGuidelines/VB/Class1.vb#34)]  
  
## <a name="see-also"></a><span data-ttu-id="9b9a2-186">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b9a2-186">See also</span></span>

- [<span data-ttu-id="9b9a2-187">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="9b9a2-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
