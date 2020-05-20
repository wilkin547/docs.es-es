---
title: Procedimiento para crear un flujo de trabajo secuencial
description: En este artículo se crea un flujo de trabajo que utiliza las actividades integradas, como la actividad de secuencia y las actividades personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5280e816-ae17-48c4-8de0-a1e6895dd8f0
ms.openlocfilehash: f80ac471fdcc425504b11b5fb17effa888aa9590
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419699"
---
# <a name="how-to-create-a-sequential-workflow"></a><span data-ttu-id="96624-103">Procedimiento para crear un flujo de trabajo secuencial</span><span class="sxs-lookup"><span data-stu-id="96624-103">How to: Create a Sequential Workflow</span></span>

<span data-ttu-id="96624-104">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="96624-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="96624-105">En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.Sequence> actividad, y las actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="96624-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Sequence> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="96624-106">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="96624-106">The workflow models a number guessing game.</span></span>

> [!NOTE]
> <span data-ttu-id="96624-107">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="96624-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="96624-108">Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="96624-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="96624-109">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="96624-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>

## <a name="to-create-the-workflow"></a><span data-ttu-id="96624-110">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-110">To create the workflow</span></span>

1. <span data-ttu-id="96624-111">Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="96624-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>

2. <span data-ttu-id="96624-112">En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="96624-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="96624-113">Seleccione **Actividad** en la lista **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="96624-113">Select **Activity** from the **Workflow** list.</span></span>

3. <span data-ttu-id="96624-114">Escriba `SequentialNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="96624-114">Type `SequentialNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>

4. <span data-ttu-id="96624-115">Arrastre una actividad **Sequence** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="96624-115">Drag a **Sequence** activity from the **Control Flow** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>

## <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="96624-116">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-116">To create the workflow variables and arguments</span></span>

1. <span data-ttu-id="96624-117">Haga doble clic en **SequentialNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="96624-117">Double-click **SequentialNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>

2. <span data-ttu-id="96624-118">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="96624-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>

3. <span data-ttu-id="96624-119">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="96624-119">Click **Create Argument**.</span></span>

4. <span data-ttu-id="96624-120">Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="96624-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>

5. <span data-ttu-id="96624-121">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="96624-121">Click **Create Argument**.</span></span>

6. <span data-ttu-id="96624-122">Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `MaxNumber` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="96624-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>

7. <span data-ttu-id="96624-123">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="96624-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>

8. <span data-ttu-id="96624-124">Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="96624-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>

9. <span data-ttu-id="96624-125">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="96624-125">Click **Create Variable**.</span></span>

    > [!TIP]
    > <span data-ttu-id="96624-126">Si no se muestra ningún cuadro **crear variable** , haga clic en la actividad **secuencia** en la superficie del diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="96624-126">If no **Create Variable** box is displayed, click the **Sequence** activity on the workflow designer surface to select it.</span></span>

10. <span data-ttu-id="96624-127">Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="96624-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

11. <span data-ttu-id="96624-128">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="96624-128">Click **Create Variable**.</span></span>

12. <span data-ttu-id="96624-129">Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="96624-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>

13. <span data-ttu-id="96624-130">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Variables**.</span><span class="sxs-lookup"><span data-stu-id="96624-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>

## <a name="to-add-the-workflow-activities"></a><span data-ttu-id="96624-131">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-131">To add the workflow activities</span></span>

1. <span data-ttu-id="96624-132">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **Sequence** .</span><span class="sxs-lookup"><span data-stu-id="96624-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Sequence** activity.</span></span> <span data-ttu-id="96624-133">Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="96624-133">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

    ```vb
    New System.Random().Next(1, MaxNumber + 1)
    ```

    ```csharp
    new System.Random().Next(1, MaxNumber + 1)
    ```

    > [!TIP]
    > <span data-ttu-id="96624-134">Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="96624-134">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>

2. <span data-ttu-id="96624-135">Arrastre una actividad **While** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en el flujo de trabajo para que esté debajo de la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="96624-135">Drag a **DoWhile** activity from the **Control Flow** section of the **Toolbox** and drop it on the workflow so that it is below the **Assign** activity.</span></span>

3. <span data-ttu-id="96624-136">Escriba la siguiente expresión en el **cuadro de valor** de la propiedad **condición** de la actividad.</span><span class="sxs-lookup"><span data-stu-id="96624-136">Type the following expression into the **DoWhile** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

     <span data-ttu-id="96624-137">Una actividad <xref:System.Activities.Statements.DoWhile> ejecuta sus actividades secundarias y después evalúa su <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span><span class="sxs-lookup"><span data-stu-id="96624-137">A <xref:System.Activities.Statements.DoWhile> activity executes its child activities and then evaluates its <xref:System.Activities.Statements.DoWhile.Condition%2A>.</span></span> <span data-ttu-id="96624-138">Si <xref:System.Activities.Statements.DoWhile.Condition%2A> se evalúa como `True`, las actividades de <xref:System.Activities.Statements.DoWhile> se ejecutan de nuevo.</span><span class="sxs-lookup"><span data-stu-id="96624-138">If the <xref:System.Activities.Statements.DoWhile.Condition%2A> evaluates to `True`, then the activities in the <xref:System.Activities.Statements.DoWhile> execute again.</span></span> <span data-ttu-id="96624-139">En este ejemplo, se evalúa el intento del usuario y <xref:System.Activities.Statements.DoWhile> continúa hasta que se acierta el número.</span><span class="sxs-lookup"><span data-stu-id="96624-139">In this example, the user’s guess is evaluated and the <xref:System.Activities.Statements.DoWhile> continues until the guess is correct.</span></span>

4. <span data-ttu-id="96624-140">Arrastre una actividad **prompt** de la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la actividad **While** del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="96624-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **DoWhile** activity from the previous step.</span></span>

5. <span data-ttu-id="96624-141">En la **ventana Propiedades**, escriba `"EnterGuess"` entre comillas en el cuadro de valor de la propiedad **BookmarkName** para la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="96624-141">In the **Properties Window**, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box for the **Prompt** activity.</span></span> <span data-ttu-id="96624-142">Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="96624-142">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>

    ```vb
    "Please enter a number between 1 and " & MaxNumber
    ```

    ```csharp
    "Please enter a number between 1 and " + MaxNumber
    ```

    > [!TIP]
    > <span data-ttu-id="96624-143">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="96624-143">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>

6. <span data-ttu-id="96624-144">Arrastre una actividad **assign** desde la sección **primitivas** del **cuadro de herramientas** y colóquela en la actividad **While** para que siga la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="96624-144">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it in the **DoWhile** activity so that it follows the **Prompt** activity.</span></span>

    > [!NOTE]
    > <span data-ttu-id="96624-145">Al quitar la actividad **assign** , observe cómo el diseñador de flujo de trabajo agrega automáticamente una actividad **Sequence** para que contenga la actividad **prompt** y la actividad **assign** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="96624-145">When you drop the **Assign** activity, note how the workflow designer automatically adds a **Sequence** activity to contain both the **Prompt** activity and the newly added **Assign** activity.</span></span>

7. <span data-ttu-id="96624-146">Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="96624-146">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>

8. <span data-ttu-id="96624-147">Arrastre una actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la actividad **Sequence** para que siga la actividad **assign** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="96624-147">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Sequence** activity so that it follows the newly added **Assign** activity.</span></span>

9. <span data-ttu-id="96624-148">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** .</span><span class="sxs-lookup"><span data-stu-id="96624-148">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>

    ```vb
    Guess <> Target
    ```

    ```csharp
    Guess != Target
    ```

10. <span data-ttu-id="96624-149">Arrastre otra actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la sección **then** de la primera actividad **If** .</span><span class="sxs-lookup"><span data-stu-id="96624-149">Drag another **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Then** section of the first **If** activity.</span></span>

11. <span data-ttu-id="96624-150">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** recién agregada.</span><span class="sxs-lookup"><span data-stu-id="96624-150">Type the following expression into the newly added **If** activity’s **Condition** property value box.</span></span>

    ```text
    Guess < Target
    ```

12. <span data-ttu-id="96624-151">Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que una esté en la sección **then** de la actividad **If** recién agregada, y otra esté en la sección **else** .</span><span class="sxs-lookup"><span data-stu-id="96624-151">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the newly added **If** activity, and one is in the **Else** section.</span></span>

13. <span data-ttu-id="96624-152">Haga clic en la actividad **WriteLine** en la sección **then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Text** .</span><span class="sxs-lookup"><span data-stu-id="96624-152">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too low."
    ```

14. <span data-ttu-id="96624-153">Haga clic en la actividad **WriteLine** en la sección **otro** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="96624-153">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>

    ```text
    "Your guess is too high."
    ```

     <span data-ttu-id="96624-154">En el ejemplo siguiente se muestra el flujo de trabajo completado:</span><span class="sxs-lookup"><span data-stu-id="96624-154">The following example illustrates the completed workflow:</span></span>

     ![Captura de pantalla que muestra el flujo de trabajo secuencial completado.](./media/how-to-create-a-sequential-workflow/complete-sequential-workflow.jpg)

## <a name="to-build-the-workflow"></a><span data-ttu-id="96624-156">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-156">To build the workflow</span></span>

1. <span data-ttu-id="96624-157">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="96624-157">Press CTRL+SHIFT+B to build the solution.</span></span>

     <span data-ttu-id="96624-158">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="96624-158">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="96624-159">Si ya ha completado el paso [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo secuencial de este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="96624-159">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the sequential workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="96624-160">Consulta también</span><span class="sxs-lookup"><span data-stu-id="96624-160">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="96624-161">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="96624-161">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="96624-162">Diseñar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-162">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="96624-163">Tutorial de Introducción</span><span class="sxs-lookup"><span data-stu-id="96624-163">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="96624-164">Procedimiento para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="96624-164">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="96624-165">Procedimiento para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96624-165">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
