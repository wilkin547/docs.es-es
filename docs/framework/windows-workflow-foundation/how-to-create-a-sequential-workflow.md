---
title: Filtrar Creación de un flujo de trabajo secuencial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 3991c16e00f1cbb4f8c1f2c8391f89ea51c1e6f2
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463805"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="dde65-102">Filtrar Creación de un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="dde65-102">How to: Create a Sequential Workflow</span></span>
<span data-ttu-id="dde65-103">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="dde65-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="dde65-104">En este tema le ayudará a crear un flujo de trabajo que usa tanto las actividades integradas, como el <xref:System.Activities.Statements.Sequence> actividad y las actividades personalizadas del anterior [Cómo: Crear una actividad](how-to-create-an-activity.md) tema.</span><span class="sxs-lookup"><span data-stu-id="dde65-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="dde65-105">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="dde65-105">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dde65-106">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="dde65-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="dde65-107">Para completar este tema, primero debe completar [Cómo: Crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="dde65-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dde65-108">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="dde65-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="to-create-the-workflow"></a><span data-ttu-id="dde65-109">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-109">To create the workflow</span></span>  
  
1.  <span data-ttu-id="dde65-110">Haga clic en **NumberGuessWorkflowActivities** en **el Explorador de soluciones** y seleccione **agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="dde65-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2.  <span data-ttu-id="dde65-111">En el **instalado**, **elementos comunes** nodo, seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="dde65-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="dde65-112">Seleccione **actividad** desde el **flujo de trabajo** lista.</span><span class="sxs-lookup"><span data-stu-id="dde65-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3.  <span data-ttu-id="dde65-113">Tipo `SequentialNumberGuessWorkflow` en el **nombre** y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="dde65-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4.  <span data-ttu-id="dde65-114">Arrastre un **secuencia** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en la **colocar actividad aquí** etiquetar en el superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dde65-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="dde65-115">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-115">To create the workflow variables and arguments</span></span>  
  
1.  <span data-ttu-id="dde65-116">Haga doble clic en **SequentialNumberGuessWorkflow.xaml** en **el Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="dde65-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2.  <span data-ttu-id="dde65-117">Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de flujo de trabajo para mostrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="dde65-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3.  <span data-ttu-id="dde65-118">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="dde65-118">Click **Create Argument**.</span></span>  
  
4.  <span data-ttu-id="dde65-119">Tipo `MaxNumber` en el **nombre** cuadro, seleccione **en** desde el **dirección** lista desplegable, seleccione **Int32** desde el **Tipo de argumento** lista desplegable y, a continuación, presione ENTRAR para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="dde65-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5.  <span data-ttu-id="dde65-120">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="dde65-120">Click **Create Argument**.</span></span>  
  
6.  <span data-ttu-id="dde65-121">Tipo `Turns` en el **nombre** cuadro que se encuentra debajo de la recién agregada `MaxNumber` argumento, seleccione **Out** desde el **dirección** lista desplegable, seleccione  **Int32** desde el **tipo de argumento** lista desplegable y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="dde65-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="dde65-122">Haga clic en **argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **argumentos** panel.</span><span class="sxs-lookup"><span data-stu-id="dde65-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8.  <span data-ttu-id="dde65-123">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de flujo de trabajo para mostrar el **Variables** panel.</span><span class="sxs-lookup"><span data-stu-id="dde65-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="dde65-124">Haga clic en **crear Variable**.</span><span class="sxs-lookup"><span data-stu-id="dde65-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="dde65-125">Si no hay ningún **crear Variable** se muestra el cuadro, haga clic en el **secuencia** actividad en la superficie del Diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="dde65-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="dde65-126">Tipo `Guess` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="dde65-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="dde65-127">Haga clic en **crear Variable**.</span><span class="sxs-lookup"><span data-stu-id="dde65-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="dde65-128">Tipo `Target` en el **nombre** cuadro, seleccione **Int32** desde el **tipo de Variable** lista desplegable y, a continuación, presione ENTRAR para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="dde65-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="dde65-129">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el **Variables** panel.</span><span class="sxs-lookup"><span data-stu-id="dde65-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="dde65-130">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-130">To add the workflow activities</span></span>  
  
1.  <span data-ttu-id="dde65-131">Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquela en la **secuencia** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="dde65-132">Tipo `Target` en el **a** cuadro y la siguiente expresión en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.</span><span class="sxs-lookup"><span data-stu-id="dde65-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="dde65-133">Si el **cuadro de herramientas** no se muestra la ventana, seleccione **cuadro de herramientas** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="dde65-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
2.  <span data-ttu-id="dde65-134">Arrastre un **DoWhile** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquela en el flujo de trabajo para que quede por debajo de la **asignar** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>  
  
3.  <span data-ttu-id="dde65-135">Escriba la siguiente expresión en el **DoWhile** la actividad **condición** cuadro del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
     <span data-ttu-id="dde65-136">Una actividad <xref:System.Activities.Statements.DoWhile> ejecuta sus actividades secundarias y después evalúa su <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="dde65-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="dde65-137">Si <xref:System.Activities.Statements.DoWhile.Condition%2A> se evalúa como `True`, las actividades de <xref:System.Activities.Statements.DoWhile> se ejecutan de nuevo.</span><span class="sxs-lookup"><span data-stu-id="dde65-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="dde65-138">En este ejemplo, se evalúa el intento del usuario y <xref:System.Activities.Statements.DoWhile> continúa hasta que se acierta el número.</span><span class="sxs-lookup"><span data-stu-id="dde65-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>  
  
4.  <span data-ttu-id="dde65-139">Arrastre un **Prompt** actividad desde la **NumberGuessWorkflowActivities** sección de la **cuadro de herramientas** y colóquelo el **DoWhile** actividad en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="dde65-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>  
  
5.  <span data-ttu-id="dde65-140">En el **ventana propiedades**, tipo `"EnterGuess"` , incluidas las comillas en el **BookmarkName** cuadro del valor de propiedad para el **Prompt** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="dde65-141">Tipo `Guess` en el **resultado** propiedad cuadro de valor y escriba la siguiente expresión en el **texto** cuadro de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    >  <span data-ttu-id="dde65-142">Si el **ventana propiedades** no se muestra, seleccione **ventana propiedades** desde el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="dde65-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
6.  <span data-ttu-id="dde65-143">Arrastre un **asignar** actividad desde la **primitivas** sección de la **cuadro de herramientas** y colóquelo el **DoWhile** actividad para que siga a la **Prompt** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dde65-144">Al colocar el **asignar** actividad, tenga en cuenta cómo el Diseñador de flujo de trabajo agrega automáticamente un **secuencia** actividad para contener el **Prompt** recién agregada y actividad **Asignar** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>  
  
7.  <span data-ttu-id="dde65-145">Tipo `Turns` en el **a** cuadro y `Turns + 1` en el **escriba una expresión de C#** o **escriba una expresión de VB** cuadro.</span><span class="sxs-lookup"><span data-stu-id="dde65-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
8.  <span data-ttu-id="dde65-146">Arrastre un **si** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquelo el **secuencia** actividad para que siga a la agregados recientemente **asignar** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>  
  
9. <span data-ttu-id="dde65-147">Escriba la siguiente expresión en el **si** la actividad **condición** cuadro del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
10. <span data-ttu-id="dde65-148">Arrastre otro **si** actividad desde la **flujo de Control** sección de la **cuadro de herramientas** y colóquelo el **, a continuación,** sección de la primera **Si** actividad.</span><span class="sxs-lookup"><span data-stu-id="dde65-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>  
  
11. <span data-ttu-id="dde65-149">Escriba la siguiente expresión en la recién agregada **si** la actividad **condición** cuadro del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>  
  
    ```
    Guess < Target  
    ```  
  
12. <span data-ttu-id="dde65-150">Arrastre dos **WriteLine** las actividades desde el **primitivas** sección de la **cuadro de herramientas** y colóquelas de modo que una esté en el **, a continuación,** sección de se ha agregado recientemente **si** actividad y otra esté en el **Else** sección.</span><span class="sxs-lookup"><span data-stu-id="dde65-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>  
  
13. <span data-ttu-id="dde65-151">Haga clic en el **WriteLine** actividad en el **, a continuación,** sección para seleccionarla y escriba la siguiente expresión en el **texto** cuadro del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
14. <span data-ttu-id="dde65-152">Haga clic en el **WriteLine** actividad en el **Else** sección para seleccionarla y escriba la siguiente expresión en el **texto** cuadro del valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="dde65-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
     <span data-ttu-id="dde65-153">El ejemplo siguiente muestra el flujo de trabajo completado:</span><span class="sxs-lookup"><span data-stu-id="dde65-153">The following example illustrates the completed workflow:</span></span>  
  
     ![Captura de pantalla que muestra el flujo de trabajo secuencial completado.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)  
  
## <a name="to-build-the-workflow"></a><span data-ttu-id="dde65-155">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-155">To build the workflow</span></span>  
  
1.  <span data-ttu-id="dde65-156">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="dde65-156">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="dde65-157">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dde65-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="dde65-158">Si ya ha completado la [Cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md) paso con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo secuencial de este paso, vaya a la [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) sección de [Cómo: Ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="dde65-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde65-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="dde65-159">See also</span></span>
- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="dde65-160">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="dde65-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="dde65-161">Diseño de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="dde65-162">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="dde65-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="dde65-163">Cómo: Crear una actividad</span><span class="sxs-lookup"><span data-stu-id="dde65-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="dde65-164">Cómo: Ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dde65-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
