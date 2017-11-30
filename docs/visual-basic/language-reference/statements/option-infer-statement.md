---
title: "Option Infer (instrucción)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: "72"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4634c198b5fc41a4834cbd3cd96f9d3f1863d09b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="option-infer-statement"></a><span data-ttu-id="d1785-102">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1785-102">Option Infer Statement</span></span>
<span data-ttu-id="d1785-103">Permite el uso de la inferencia de tipo de variable local en la declaración de variables.</span><span class="sxs-lookup"><span data-stu-id="d1785-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1785-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1785-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="d1785-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="d1785-105">Parts</span></span>  
  
|<span data-ttu-id="d1785-106">Término</span><span class="sxs-lookup"><span data-stu-id="d1785-106">Term</span></span>|<span data-ttu-id="d1785-107">Definición</span><span class="sxs-lookup"><span data-stu-id="d1785-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="d1785-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d1785-108">Optional.</span></span> <span data-ttu-id="d1785-109">Habilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="d1785-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="d1785-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d1785-110">Optional.</span></span> <span data-ttu-id="d1785-111">Deshabilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="d1785-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1785-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d1785-112">Remarks</span></span>  
 <span data-ttu-id="d1785-113">Para establecer `Option Infer` en un archivo, escriba `Option Infer On` o `Option Infer Off` en la parte superior del archivo, antes de cualquier otro código fuente.</span><span class="sxs-lookup"><span data-stu-id="d1785-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="d1785-114">Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="d1785-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="d1785-115">Al establecer `Option Infer` en `On`, puede declarar variables locales sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d1785-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="d1785-116">El compilador deduce el tipo de datos de una variable a partir del tipo de su expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="d1785-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="d1785-117">En la siguiente ilustración, `Option Infer` está activado.</span><span class="sxs-lookup"><span data-stu-id="d1785-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="d1785-118">La variable de la declaración `Dim someVar = 2` se declara como un entero mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d1785-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="d1785-119">![Vista IntelliSense de la declaración. ] (../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="d1785-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="d1785-120">IntelliSense cuando Option Infer está activado</span><span class="sxs-lookup"><span data-stu-id="d1785-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="d1785-121">En la siguiente ilustración, `Option Infer` está desactivado.</span><span class="sxs-lookup"><span data-stu-id="d1785-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="d1785-122">La variable de la declaración `Dim someVar = 2` se declara como un `Object` mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d1785-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="d1785-123">En este ejemplo, el **Option Strict** configuración está establecida en **desactivar** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d1785-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="d1785-124">![Vista IntelliSense de la declaración. ] (../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="d1785-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="d1785-125">IntelliSense cuando Option Infer está desactivado</span><span class="sxs-lookup"><span data-stu-id="d1785-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1785-126">Cuando una variable se declara como un `Object`, el tipo de tiempo de ejecución puede cambiar mientras se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="d1785-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="d1785-127">realiza operaciones llamadas *conversión boxing* y *unboxing* para realizar conversiones entre un `Object` y un tipo de valor, lo que ralentiza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d1785-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="d1785-128">Para obtener información acerca de la conversión boxing y unboxing (conversión), consulte el [especificación del lenguaje Visual Basic](../../../visual-basic/reference/language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="d1785-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification/index.md).</span></span>
  
 <span data-ttu-id="d1785-129">La inferencia de tipo se aplica en el nivel de procedimiento, y no se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="d1785-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="d1785-130">Para obtener más información, consulte [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d1785-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="d1785-131">Cuando la instrucción Option Infer no está presente</span><span class="sxs-lookup"><span data-stu-id="d1785-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="d1785-132">Si el código fuente no contiene un `Option Infer` (instrucción), el **Option Infer** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="d1785-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="d1785-133">Si se usa el compilador de línea de comandos, el [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) se utiliza la opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="d1785-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="d1785-134">Cómo establecer Option Infer en el IDE</span><span class="sxs-lookup"><span data-stu-id="d1785-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="d1785-135">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d1785-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="d1785-136">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d1785-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d1785-137">Para obtener más información, consulte [NIB: administración de propiedades del proyecto con el Diseñador de proyectos](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="d1785-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="d1785-138">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d1785-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="d1785-139">Establezca el valor el **Option infer** cuadro.</span><span class="sxs-lookup"><span data-stu-id="d1785-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="d1785-140">Cuando se crea un nuevo proyecto, el **Option Infer** en el **compilar** ficha está establecida en el **Option Infer** en el **valores predeterminados de VB** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="d1785-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="d1785-141">Para tener acceso a la **valores predeterminados de VB** cuadro de diálogo, en la **herramientas** menú, haga clic en **opciones**.</span><span class="sxs-lookup"><span data-stu-id="d1785-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="d1785-142">En el **opciones** cuadro de diálogo, expanda **proyectos y soluciones**y, a continuación, haga clic en **valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="d1785-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="d1785-143">El valor predeterminado inicial de **valores predeterminados de VB** es `On`.</span><span class="sxs-lookup"><span data-stu-id="d1785-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="d1785-144">Cómo establecer Option Infer en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d1785-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="d1785-145">Incluir el [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) opción del compilador en el **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="d1785-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="d1785-146">Tipos de datos y valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="d1785-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="d1785-147">En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.</span><span class="sxs-lookup"><span data-stu-id="d1785-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="d1785-148">¿Tipo de datos especificado?</span><span class="sxs-lookup"><span data-stu-id="d1785-148">Data type specified?</span></span>|<span data-ttu-id="d1785-149">¿Inicializador especificado?</span><span class="sxs-lookup"><span data-stu-id="d1785-149">Initializer specified?</span></span>|<span data-ttu-id="d1785-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1785-150">Example</span></span>|<span data-ttu-id="d1785-151">Resultado</span><span class="sxs-lookup"><span data-stu-id="d1785-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="d1785-152">No</span><span class="sxs-lookup"><span data-stu-id="d1785-152">No</span></span>|<span data-ttu-id="d1785-153">No</span><span class="sxs-lookup"><span data-stu-id="d1785-153">No</span></span>|`Dim qty`|<span data-ttu-id="d1785-154">Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d1785-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="d1785-155">Si `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1785-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="d1785-156">No</span><span class="sxs-lookup"><span data-stu-id="d1785-156">No</span></span>|<span data-ttu-id="d1785-157">Sí</span><span class="sxs-lookup"><span data-stu-id="d1785-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="d1785-158">Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="d1785-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="d1785-159">Vea [inferencia de tipo Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d1785-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="d1785-160">Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.</span><span class="sxs-lookup"><span data-stu-id="d1785-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="d1785-161">Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1785-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="d1785-162">Sí</span><span class="sxs-lookup"><span data-stu-id="d1785-162">Yes</span></span>|<span data-ttu-id="d1785-163">No</span><span class="sxs-lookup"><span data-stu-id="d1785-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="d1785-164">La variable se inicializa con el valor predeterminado del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d1785-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="d1785-165">Para obtener más información, consulte [Dim (instrucción)](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d1785-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="d1785-166">Sí</span><span class="sxs-lookup"><span data-stu-id="d1785-166">Yes</span></span>|<span data-ttu-id="d1785-167">Sí</span><span class="sxs-lookup"><span data-stu-id="d1785-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="d1785-168">Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d1785-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d1785-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1785-169">Example</span></span>  
 <span data-ttu-id="d1785-170">Los ejemplos siguientes muestran cómo la instrucción `Option Infer` habilita la inferencia de tipo local.</span><span class="sxs-lookup"><span data-stu-id="d1785-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]  
  
## <a name="example"></a><span data-ttu-id="d1785-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d1785-171">Example</span></span>  
 <span data-ttu-id="d1785-172">El siguiente ejemplo demuestra que el tipo en tiempo de ejecución puede ser diferente cuando una variable se identifica como un `Object`.</span><span class="sxs-lookup"><span data-stu-id="d1785-172">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d1785-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1785-173">See Also</span></span>  
 [<span data-ttu-id="d1785-174">Dim (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1785-174">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="d1785-175">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="d1785-175">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="d1785-176">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1785-176">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="d1785-177">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1785-177">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="d1785-178">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1785-178">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="d1785-179">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="d1785-179">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)  
 [<span data-ttu-id="d1785-180">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="d1785-180">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="d1785-181">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="d1785-181">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
