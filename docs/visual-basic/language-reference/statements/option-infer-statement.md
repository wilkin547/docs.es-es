---
title: Option Infer (instrucción, Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 59766999c5b03aac7aec13b293feaa8c17f2ced0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59338571"
---
# <a name="option-infer-statement"></a><span data-ttu-id="dd7ff-102">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="dd7ff-102">Option Infer Statement</span></span>
<span data-ttu-id="dd7ff-103">Permite el uso de la inferencia de tipo de variable local en la declaración de variables.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd7ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dd7ff-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="dd7ff-105">Elementos</span><span class="sxs-lookup"><span data-stu-id="dd7ff-105">Parts</span></span>  
  
|<span data-ttu-id="dd7ff-106">Término</span><span class="sxs-lookup"><span data-stu-id="dd7ff-106">Term</span></span>|<span data-ttu-id="dd7ff-107">de esquema JSON</span><span class="sxs-lookup"><span data-stu-id="dd7ff-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="dd7ff-108">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-108">Optional.</span></span> <span data-ttu-id="dd7ff-109">Habilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="dd7ff-110">Opcional.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-110">Optional.</span></span> <span data-ttu-id="dd7ff-111">Deshabilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd7ff-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd7ff-112">Remarks</span></span>  
 <span data-ttu-id="dd7ff-113">Para establecer `Option Infer` en un archivo, escriba `Option Infer On` o `Option Infer Off` en la parte superior del archivo, antes de cualquier otro código fuente.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="dd7ff-114">Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="dd7ff-115">Al establecer `Option Infer` en `On`, puede declarar variables locales sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="dd7ff-116">El compilador deduce el tipo de datos de una variable a partir del tipo de su expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="dd7ff-117">En la siguiente ilustración, `Option Infer` está activado.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="dd7ff-118">La variable de la declaración `Dim someVar = 2` se declara como un entero mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>

 <span data-ttu-id="dd7ff-119">Captura de pantalla siguiente muestra IntelliSense cuando Option Infer se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="dd7ff-119">The following screenshot shows IntelliSense when Option Infer is on:</span></span> 
  
 ![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer está activado.](./media/option-infer-statement/option-infer-as-integer-on.png)  
  
 <span data-ttu-id="dd7ff-121">En la siguiente ilustración, `Option Infer` está desactivado.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="dd7ff-122">La variable de la declaración `Dim someVar = 2` se declara como un `Object` mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="dd7ff-123">En este ejemplo, el **Option Strict** configuración está establecida en **desactivar** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dd7ff-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="dd7ff-124">Captura de pantalla siguiente muestra IntelliSense cuando Option Infer está desactivado:</span><span class="sxs-lookup"><span data-stu-id="dd7ff-124">The following screenshot shows IntelliSense when Option Infer is off:</span></span>
 
 ![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer está desactivado.](./media/option-infer-statement/option-infer-as-object-off.png)  
  
> [!NOTE]
>  <span data-ttu-id="dd7ff-126">Cuando una variable se declara como un `Object`, el tipo de tiempo de ejecución puede cambiar mientras se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="dd7ff-127">Visual Basic realiza operaciones llamadas *boxing* y *unboxing* para convertir entre un `Object` y un tipo de valor, lo que ralentiza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-127">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="dd7ff-128">Para obtener información sobre las conversiones boxing y unboxing, consulte el [especificación del lenguaje Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).</span><span class="sxs-lookup"><span data-stu-id="dd7ff-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).</span></span>
  
 <span data-ttu-id="dd7ff-129">La inferencia de tipo se aplica en el nivel de procedimiento, y no se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="dd7ff-130">Para obtener más información, consulte [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="dd7ff-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="dd7ff-131">Cuando la instrucción Option Infer no está presente</span><span class="sxs-lookup"><span data-stu-id="dd7ff-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="dd7ff-132">Si el código fuente no contiene un `Option Infer` instrucción, el **Option Infer** en el [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) se utiliza.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="dd7ff-133">Si se usa el compilador de línea de comandos, el [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) se utiliza la opción del compilador.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="dd7ff-134">Cómo establecer Option Infer en el IDE</span><span class="sxs-lookup"><span data-stu-id="dd7ff-134">To set Option Infer in the IDE</span></span>  
  
1. <span data-ttu-id="dd7ff-135">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="dd7ff-136">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-136">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="dd7ff-137">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-137">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="dd7ff-138">Establezca el valor el **Option infer** cuadro.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-138">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="dd7ff-139">Cuando se crea un nuevo proyecto, el **Option Infer** en el **compilar** ficha se establece en el **Option Infer** en el **valores predeterminados de VB** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-139">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="dd7ff-140">Para tener acceso a la **valores predeterminados de VB** cuadro de diálogo el **herramientas** menú, haga clic en **opciones**.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-140">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="dd7ff-141">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-141">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="dd7ff-142">El valor predeterminado inicial de **valores predeterminados de VB** es `On`.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-142">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="dd7ff-143">Cómo establecer Option Infer en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="dd7ff-143">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="dd7ff-144">Incluir el [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) opción del compilador en el **vbc** comando.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-144">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="dd7ff-145">Tipos de datos y valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="dd7ff-145">Default Data Types and Values</span></span>  
 <span data-ttu-id="dd7ff-146">En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-146">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="dd7ff-147">¿Tipo de datos especificado?</span><span class="sxs-lookup"><span data-stu-id="dd7ff-147">Data type specified?</span></span>|<span data-ttu-id="dd7ff-148">¿Inicializador especificado?</span><span class="sxs-lookup"><span data-stu-id="dd7ff-148">Initializer specified?</span></span>|<span data-ttu-id="dd7ff-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd7ff-149">Example</span></span>|<span data-ttu-id="dd7ff-150">Resultado</span><span class="sxs-lookup"><span data-stu-id="dd7ff-150">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="dd7ff-151">No</span><span class="sxs-lookup"><span data-stu-id="dd7ff-151">No</span></span>|<span data-ttu-id="dd7ff-152">No</span><span class="sxs-lookup"><span data-stu-id="dd7ff-152">No</span></span>|`Dim qty`|<span data-ttu-id="dd7ff-153">Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-153">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="dd7ff-154">Si `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-154">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="dd7ff-155">No</span><span class="sxs-lookup"><span data-stu-id="dd7ff-155">No</span></span>|<span data-ttu-id="dd7ff-156">Sí</span><span class="sxs-lookup"><span data-stu-id="dd7ff-156">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="dd7ff-157">Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-157">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="dd7ff-158">Consulte [inferencia de tipos Local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="dd7ff-158">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="dd7ff-159">Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-159">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="dd7ff-160">Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-160">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="dd7ff-161">Sí</span><span class="sxs-lookup"><span data-stu-id="dd7ff-161">Yes</span></span>|<span data-ttu-id="dd7ff-162">No</span><span class="sxs-lookup"><span data-stu-id="dd7ff-162">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="dd7ff-163">La variable se inicializa con el valor predeterminado del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-163">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="dd7ff-164">Para obtener más información, consulte [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="dd7ff-164">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="dd7ff-165">Sí</span><span class="sxs-lookup"><span data-stu-id="dd7ff-165">Yes</span></span>|<span data-ttu-id="dd7ff-166">Sí</span><span class="sxs-lookup"><span data-stu-id="dd7ff-166">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="dd7ff-167">Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-167">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd7ff-168">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd7ff-168">Example</span></span>  
 <span data-ttu-id="dd7ff-169">Los ejemplos siguientes muestran cómo la instrucción `Option Infer` habilita la inferencia de tipo local.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-169">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="dd7ff-170">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd7ff-170">Example</span></span>  
 <span data-ttu-id="dd7ff-171">El siguiente ejemplo demuestra que el tipo en tiempo de ejecución puede ser diferente cuando una variable se identifica como un `Object`.</span><span class="sxs-lookup"><span data-stu-id="dd7ff-171">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="dd7ff-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd7ff-172">See also</span></span>

- [<span data-ttu-id="dd7ff-173">Dim (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="dd7ff-173">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="dd7ff-174">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="dd7ff-174">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="dd7ff-175">Option Compare (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="dd7ff-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="dd7ff-176">Option Explicit (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="dd7ff-176">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="dd7ff-177">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="dd7ff-177">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="dd7ff-178">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="dd7ff-178">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="dd7ff-179">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="dd7ff-179">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="dd7ff-180">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="dd7ff-180">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
