---
title: Procedimiento para crear un flujo de trabajo secuencial
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: 61e3f01b1259536ff15d71526e91aef42069722e
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989703"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="69213-102">Procedimiento para crear un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="69213-102">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="69213-103">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="69213-103">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="69213-104">En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas <xref:System.Activities.Statements.Sequence> , como la actividad, y las actividades personalizadas [de los procedimientos anteriores: Cree un tema](how-to-create-an-activity.md) de la actividad.</span><span class="sxs-lookup"><span data-stu-id="69213-104">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="69213-105">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="69213-105">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="69213-106">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="69213-106">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="69213-107">Para completar este tema, primero debe completar [el procedimiento: Cree una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="69213-107">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="69213-108">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="69213-108">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="69213-109">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-109">To create the workflow</span></span>

1. <span data-ttu-id="69213-110">Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="69213-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="69213-111">En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="69213-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="69213-112">Seleccione **actividad** en la lista **flujo de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="69213-112">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="69213-113">Escriba `SequentialNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="69213-113">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="69213-114">Arrastre una actividad **Sequence** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69213-114">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="69213-115">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-115">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="69213-116">Haga doble clic en **SequentialNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="69213-116">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="69213-117">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="69213-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="69213-118">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="69213-118">Click **Create Argument**.</span></span>

4. <span data-ttu-id="69213-119">Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="69213-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="69213-120">Haga clic en **crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="69213-120">Click **Create Argument**.</span></span>

6. <span data-ttu-id="69213-121">Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento `MaxNumber` recién agregado, seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="69213-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="69213-122">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="69213-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="69213-123">Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="69213-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="69213-124">Haga clic en **crear variable**.</span><span class="sxs-lookup"><span data-stu-id="69213-124">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="69213-125">Si no se muestra ningún cuadro **crear variable** , haga clic en la actividad **secuencia** en la superficie del diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="69213-125">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="69213-126">Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="69213-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="69213-127">Haga clic en **crear variable**.</span><span class="sxs-lookup"><span data-stu-id="69213-127">Click **Create Variable**.</span></span>

12. <span data-ttu-id="69213-128">Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="69213-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="69213-129">Haga clic en **variables** en el lado inferior izquierdo del diseñador de actividad para cerrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="69213-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="69213-130">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-130">To add the workflow activities</span></span>

1. <span data-ttu-id="69213-131">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="69213-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="69213-132">Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="69213-132">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="69213-133">Si no se muestra la ventana **cuadro de herramientas** , seleccione **cuadro de herramientas** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="69213-133">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="69213-134">Arrastre una actividad **While** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en el flujo de trabajo para que esté debajo de la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="69213-134">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="69213-135">Escriba la siguiente expresión en el **cuadro de valor** de la propiedad **condición** de la actividad.</span><span class="sxs-lookup"><span data-stu-id="69213-135">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="69213-136">Una actividad <xref:System.Activities.Statements.DoWhile> ejecuta sus actividades secundarias y después evalúa su <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="69213-136">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="69213-137">Si <xref:System.Activities.Statements.DoWhile.Condition%2A> se evalúa como `True`, las actividades de <xref:System.Activities.Statements.DoWhile> se ejecutan de nuevo.</span><span class="sxs-lookup"><span data-stu-id="69213-137">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="69213-138">En este ejemplo, se evalúa el intento del usuario y <xref:System.Activities.Statements.DoWhile> continúa hasta que se acierta el número.</span><span class="sxs-lookup"><span data-stu-id="69213-138">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="69213-139">Arrastre una actividad **prompt** de la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **While** del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="69213-139">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="69213-140">En la **ventana Propiedades**, escriba `"EnterGuess"` entre comillas en el cuadro de valor de la propiedad **BookmarkName** para la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="69213-140">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="69213-141">Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="69213-141">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="69213-142">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="69213-142">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="69213-143">Arrastre una actividad **assign** desde la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **While** para que siga la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="69213-143">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="69213-144">Al quitar la actividad **assign** , observe cómo el diseñador de flujo de trabajo agrega automáticamente una actividad **Sequence** para que contenga la actividad **prompt** y la actividad **assign** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="69213-144">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="69213-145">Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba C# una expresión** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="69213-145">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="69213-146">Arrastre una actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga la actividad **assign** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="69213-146">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="69213-147">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** .</span><span class="sxs-lookup"><span data-stu-id="69213-147">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="69213-148">Arrastre otra actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la sección **then** de la primera actividad **If** .</span><span class="sxs-lookup"><span data-stu-id="69213-148">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="69213-149">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="69213-149">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="69213-150">Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que una esté en la sección **then** de la actividad **If** recién agregada, y otra esté en la sección **else** .</span><span class="sxs-lookup"><span data-stu-id="69213-150">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="69213-151">Haga clic en la actividad **WriteLine** en la sección **then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Text** .</span><span class="sxs-lookup"><span data-stu-id="69213-151">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="69213-152">Haga clic en la actividad **WriteLine** en la sección **otro** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="69213-152">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="69213-153">En el ejemplo siguiente se muestra el flujo de trabajo completado:</span><span class="sxs-lookup"><span data-stu-id="69213-153">The following example illustrates the completed workflow:</span></span>

     ![Captura de pantalla que muestra el flujo de trabajo secuencial completado.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="69213-155">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-155">To build the workflow</span></span>

1. <span data-ttu-id="69213-156">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="69213-156">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="69213-157">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, consulte el tema siguiente [, How to: Ejecutar un flujo](how-to-run-a-workflow.md)de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69213-157">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="69213-158">Si ya ha completado el [procedimiento: Ejecutar un paso](how-to-run-a-workflow.md) de flujo de trabajo con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo secuencial desde este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [cómo: Ejecutar un flujo](how-to-run-a-workflow.md)de trabajo.</span><span class="sxs-lookup"><span data-stu-id="69213-158">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69213-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="69213-159">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="69213-160">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="69213-160">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="69213-161">Diseño de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-161">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="69213-162">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="69213-162">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="69213-163">Cómo: Crear una actividad</span><span class="sxs-lookup"><span data-stu-id="69213-163">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="69213-164">Procedimientos: Ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="69213-164">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
