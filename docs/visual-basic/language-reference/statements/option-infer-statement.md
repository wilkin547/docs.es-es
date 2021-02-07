---
description: 'Más información acerca de: Option Infer (instrucción)'
title: Option Infer (instrucción)
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
ms.openlocfilehash: d0c3de7bdafb7e9b361da7a8538046e3d76b5ce7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741593"
---
# <a name="option-infer-statement"></a><span data-ttu-id="d4a2c-103">Option Infer (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4a2c-103">Option Infer Statement</span></span>

<span data-ttu-id="d4a2c-104">Permite el uso de la inferencia de tipo de variable local en la declaración de variables.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-104">Enables the use of local type inference in declaring variables.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4a2c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d4a2c-105">Syntax</span></span>

```vb
Option Infer { On | Off }
```

## <a name="parts"></a><span data-ttu-id="d4a2c-106">Partes</span><span class="sxs-lookup"><span data-stu-id="d4a2c-106">Parts</span></span>

|<span data-ttu-id="d4a2c-107">Término</span><span class="sxs-lookup"><span data-stu-id="d4a2c-107">Term</span></span>|<span data-ttu-id="d4a2c-108">Definición</span><span class="sxs-lookup"><span data-stu-id="d4a2c-108">Definition</span></span>|
|---|---|
|`On`|<span data-ttu-id="d4a2c-109">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-109">Optional.</span></span> <span data-ttu-id="d4a2c-110">Habilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-110">Enables local type inference.</span></span>|
|`Off`|<span data-ttu-id="d4a2c-111">Opcional.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-111">Optional.</span></span> <span data-ttu-id="d4a2c-112">Deshabilita la inferencia de tipo de variable local.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-112">Disables local type inference.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d4a2c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4a2c-113">Remarks</span></span>

<span data-ttu-id="d4a2c-114">Para establecer `Option Infer` en un archivo, escriba `Option Infer On` o `Option Infer Off` en la parte superior del archivo, antes de cualquier otro código fuente.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-114">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="d4a2c-115">Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-115">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>

<span data-ttu-id="d4a2c-116">Al establecer `Option Infer` en `On`, puede declarar variables locales sin especificar explícitamente un tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-116">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="d4a2c-117">El compilador deduce el tipo de datos de una variable a partir del tipo de su expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-117">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>

<span data-ttu-id="d4a2c-118">En la siguiente ilustración, `Option Infer` está activado.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-118">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="d4a2c-119">La variable de la declaración `Dim someVar = 2` se declara como un entero mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-119">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>

<span data-ttu-id="d4a2c-120">En la captura de pantalla siguiente se muestra IntelliSense cuando Option Infer está activada:</span><span class="sxs-lookup"><span data-stu-id="d4a2c-120">The following screenshot shows IntelliSense when Option Infer is on:</span></span>

![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer está activada.](./media/option-infer-statement/option-infer-as-integer-on.png)

<span data-ttu-id="d4a2c-122">En la siguiente ilustración, `Option Infer` está desactivado.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-122">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="d4a2c-123">La variable de la declaración `Dim someVar = 2` se declara como un `Object` mediante la inferencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-123">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="d4a2c-124">En este ejemplo, el valor **Option Strict** está establecido en **OFF** en la [Página compilar, diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="d4a2c-124">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>

<span data-ttu-id="d4a2c-125">La captura de pantalla siguiente muestra IntelliSense cuando Option Infer es OFF:</span><span class="sxs-lookup"><span data-stu-id="d4a2c-125">The following screenshot shows IntelliSense when Option Infer is off:</span></span>

![Captura de pantalla que muestra la vista de IntelliSense cuando Option Infer es OFF.](./media/option-infer-statement/option-infer-as-object-off.png)

> [!NOTE]
> <span data-ttu-id="d4a2c-127">Cuando una variable se declara como un `Object`, el tipo de tiempo de ejecución puede cambiar mientras se ejecuta el programa.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-127">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="d4a2c-128">Visual Basic realiza operaciones llamadas *Boxing* y *unboxing* para realizar la conversión entre un `Object` y un tipo de valor, lo que hace que la ejecución sea más lenta.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-128">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="d4a2c-129">Para obtener información sobre las conversiones boxing y unboxing, vea la [especificación del lenguaje Visual Basic](~/_vblang/spec/conversions.md#value-type-conversions).</span><span class="sxs-lookup"><span data-stu-id="d4a2c-129">For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).</span></span>

<span data-ttu-id="d4a2c-130">La inferencia de tipo se aplica en el nivel de procedimiento, y no se aplica fuera de un procedimiento en una clase, estructura, módulo o interfaz.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-130">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>

<span data-ttu-id="d4a2c-131">Para obtener más información, consulte [inferencia de tipo de local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d4a2c-131">For additional information, see [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>

## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="d4a2c-132">Cuando la instrucción Option Infer no está presente</span><span class="sxs-lookup"><span data-stu-id="d4a2c-132">When an Option Infer Statement Is Not Present</span></span>

<span data-ttu-id="d4a2c-133">Si el código fuente no contiene una `Option Infer` instrucción, se utiliza la configuración **Option Infer** en la [Página compilar, el diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-133">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="d4a2c-134">Si se usa el compilador de línea de comandos, se usa la opción del compilador [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-134">If the command-line compiler is used, the [-optioninfer](../../reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>

#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="d4a2c-135">Cómo establecer Option Infer en el IDE</span><span class="sxs-lookup"><span data-stu-id="d4a2c-135">To set Option Infer in the IDE</span></span>

1. <span data-ttu-id="d4a2c-136">En el **Explorador de soluciones**, seleccione un proyecto.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-136">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="d4a2c-137">En el menú **Proyecto**, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-137">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="d4a2c-138">Haga clic en la pestaña **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-138">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="d4a2c-139">Establezca el valor en el cuadro **Option Infer** .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-139">Set the value in the **Option infer** box.</span></span>

<span data-ttu-id="d4a2c-140">Al crear un nuevo proyecto, el valor **Option Infer** de la pestaña **compilar** se establece en el valor **Option Infer** del cuadro de diálogo **valores predeterminados de VB** .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="d4a2c-141">Para tener acceso al cuadro de diálogo **valores predeterminados de VB** , en el menú **herramientas** , haga clic en **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="d4a2c-142">En el cuadro de diálogo **Opciones**, expanda **Proyectos y soluciones** y, después, haga clic en **Valores predeterminados de VB**.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="d4a2c-143">La configuración predeterminada inicial en los **valores predeterminados de VB** es `On` .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-143">The initial default setting in **VB Defaults** is `On`.</span></span>

#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="d4a2c-144">Cómo establecer Option Infer en la línea de comandos</span><span class="sxs-lookup"><span data-stu-id="d4a2c-144">To set Option Infer on the command line</span></span>

<span data-ttu-id="d4a2c-145">Incluya la opción del compilador [-optioninfer (](../../reference/command-line-compiler/optioninfer.md) en el comando **VBC** .</span><span class="sxs-lookup"><span data-stu-id="d4a2c-145">Include the [-optioninfer](../../reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>

## <a name="default-data-types-and-values"></a><span data-ttu-id="d4a2c-146">Tipos de datos y valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="d4a2c-146">Default Data Types and Values</span></span>

<span data-ttu-id="d4a2c-147">En la tabla siguiente se describen los resultados de diversas combinaciones resultantes de especificar el tipo de datos y el inicializador en una instrucción `Dim`.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>

|<span data-ttu-id="d4a2c-148">¿Tipo de datos especificado?</span><span class="sxs-lookup"><span data-stu-id="d4a2c-148">Data type specified?</span></span>|<span data-ttu-id="d4a2c-149">¿Inicializador especificado?</span><span class="sxs-lookup"><span data-stu-id="d4a2c-149">Initializer specified?</span></span>|<span data-ttu-id="d4a2c-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4a2c-150">Example</span></span>|<span data-ttu-id="d4a2c-151">Resultado</span><span class="sxs-lookup"><span data-stu-id="d4a2c-151">Result</span></span>|
|---|---|---|---|
|<span data-ttu-id="d4a2c-152">No</span><span class="sxs-lookup"><span data-stu-id="d4a2c-152">No</span></span>|<span data-ttu-id="d4a2c-153">No</span><span class="sxs-lookup"><span data-stu-id="d4a2c-153">No</span></span>|`Dim qty`|<span data-ttu-id="d4a2c-154">Si `Option Strict` está desactivado (valor predeterminado), la variable se establece en `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="d4a2c-155">Si `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="d4a2c-156">No</span><span class="sxs-lookup"><span data-stu-id="d4a2c-156">No</span></span>|<span data-ttu-id="d4a2c-157">Sí</span><span class="sxs-lookup"><span data-stu-id="d4a2c-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="d4a2c-158">Si `Option Infer` está activado (valor predeterminado), la variable toma el tipo de datos del inicializador.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="d4a2c-159">Vea [inferencia de tipo de local](../../programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="d4a2c-159">See [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="d4a2c-160">Si `Option Infer` está desactivado y `Option Strict` está desactivado, la variable toma el tipo de datos de `Object`.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="d4a2c-161">Si `Option Infer` está desactivado y `Option Strict` está activado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|
|<span data-ttu-id="d4a2c-162">Sí</span><span class="sxs-lookup"><span data-stu-id="d4a2c-162">Yes</span></span>|<span data-ttu-id="d4a2c-163">No</span><span class="sxs-lookup"><span data-stu-id="d4a2c-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="d4a2c-164">La variable se inicializa con el valor predeterminado del tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="d4a2c-165">Para obtener más información, vea [Dim (instrucción](dim-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="d4a2c-165">For more information, see [Dim Statement](dim-statement.md).</span></span>|
|<span data-ttu-id="d4a2c-166">Sí</span><span class="sxs-lookup"><span data-stu-id="d4a2c-166">Yes</span></span>|<span data-ttu-id="d4a2c-167">Sí</span><span class="sxs-lookup"><span data-stu-id="d4a2c-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="d4a2c-168">Si el tipo de datos del inicializador no es convertible al tipo de datos especificado, se produce un error en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|

## <a name="example"></a><span data-ttu-id="d4a2c-169">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4a2c-169">Example</span></span>

<span data-ttu-id="d4a2c-170">Los ejemplos siguientes muestran cómo la instrucción `Option Infer` habilita la inferencia de tipo local.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>

[!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]

## <a name="example"></a><span data-ttu-id="d4a2c-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d4a2c-171">Example</span></span>

<span data-ttu-id="d4a2c-172">El siguiente ejemplo demuestra que el tipo en tiempo de ejecución puede ser diferente cuando una variable se identifica como un `Object`.</span><span class="sxs-lookup"><span data-stu-id="d4a2c-172">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>

[!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]

## <a name="see-also"></a><span data-ttu-id="d4a2c-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4a2c-173">See also</span></span>

- [<span data-ttu-id="d4a2c-174">Instrucción Dim</span><span class="sxs-lookup"><span data-stu-id="d4a2c-174">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="d4a2c-175">Inferencia de tipo de variable local</span><span class="sxs-lookup"><span data-stu-id="d4a2c-175">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="d4a2c-176">Option Compare (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4a2c-176">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="d4a2c-177">Option Explicit (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4a2c-177">Option Explicit Statement</span></span>](option-explicit-statement.md)
- [<span data-ttu-id="d4a2c-178">Option Strict (instrucción)</span><span class="sxs-lookup"><span data-stu-id="d4a2c-178">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="d4a2c-179">Valores predeterminados de Visual Basic, Proyectos, Opciones (Cuadro de diálogo)</span><span class="sxs-lookup"><span data-stu-id="d4a2c-179">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="d4a2c-180">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="d4a2c-180">-optioninfer</span></span>](../../reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="d4a2c-181">Conversión boxing y conversión unboxing</span><span class="sxs-lookup"><span data-stu-id="d4a2c-181">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
