---
title: Procedimiento para crear un flujo de trabajo de diagrama de flujo
description: En este artículo se describe la creación de un flujo de trabajo que utiliza las actividades integradas y las actividades personalizadas del artículo anterior.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: eb30a3a21ffc4cffe64d2f5d0bc741728f1ea87d
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190486"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="06612-103">Procedimiento para crear un flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="06612-103">How to: Create a Flowchart Workflow</span></span>

<span data-ttu-id="06612-104">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="06612-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="06612-105">En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.Flowchart> actividad, y las actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="06612-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="06612-106">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="06612-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06612-107">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="06612-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="06612-108">Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="06612-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="06612-109">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="06612-110">Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="06612-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="06612-111">En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="06612-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="06612-112">Seleccione **Actividad** en la lista **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="06612-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="06612-113">Escriba `FlowchartNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="06612-113">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="06612-114">Arrastre una actividad de **Diagrama de flujo** desde la sección **Diagrama** de flujo del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="06612-114">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="06612-115">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="06612-116">Haga doble clic en **FlowchartNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="06612-116">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="06612-117">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="06612-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="06612-118">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="06612-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="06612-119">Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="06612-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="06612-120">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="06612-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="06612-121">Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `MaxNumber` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="06612-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="06612-122">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="06612-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="06612-123">Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="06612-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="06612-124">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="06612-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="06612-125">Si no se muestra ningún cuadro **crear variable** , haga clic en la <xref:System.Activities.Statements.Flowchart> actividad en la superficie del diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="06612-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="06612-126">Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="06612-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="06612-127">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="06612-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="06612-128">Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="06612-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="06612-129">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Variables**.</span><span class="sxs-lookup"><span data-stu-id="06612-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="06612-130">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="06612-131">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y mantenga el mouse sobre el nodo **iniciar** , que se encuentra en la parte superior del diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="06612-131">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="06612-132">Cuando la actividad de **asignación** está sobre el nodo de **Inicio** , aparecen tres triángulos alrededor del nodo de **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="06612-132">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="06612-133">Coloque la actividad **assign** en el triángulo que está justo debajo del nodo de **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="06612-133">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="06612-134">Se vincularán los dos elementos juntos y se designará la actividad **assign** como la primera actividad del diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="06612-134">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="06612-135">Las actividades también se pueden indicar como actividad de inicio en el flujo de trabajo si se vinculan manualmente al nodo de inicio.</span><span class="sxs-lookup"><span data-stu-id="06612-135">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="06612-136">Para ello, mantenga el mouse sobre el nodo de **Inicio** , haga clic en uno de los rectángulos que aparecen cuando el mouse está sobre el nodo de **Inicio** y arrastre la línea de conexión hacia abajo hasta la actividad deseada y colóquela en uno de los rectángulos que aparecen.</span><span class="sxs-lookup"><span data-stu-id="06612-136">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="06612-137">También puede designar una actividad como la actividad de inicio; para ello, haga clic con el botón secundario en ella y elija **establecer como nodo de inicio**.</span><span class="sxs-lookup"><span data-stu-id="06612-137">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="06612-138">Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="06612-138">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="06612-139">Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="06612-139">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="06612-140">Arrastre una actividad **prompt** de la **sección NumberGuessWorkflowActivities** del cuadro de **herramientas**, colóquela debajo de la actividad **assign** del paso anterior y conecte la actividad **prompt** a la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="06612-140">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="06612-141">Hay tres maneras de conectar las dos actividades.</span><span class="sxs-lookup"><span data-stu-id="06612-141">There are three ways to connect the two activities.</span></span> <span data-ttu-id="06612-142">La primera manera es conectarlas a medida que se coloca la actividad **prompt** en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="06612-142">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="06612-143">Cuando arrastre la actividad **prompt** al flujo de trabajo, mantenga el mouse sobre la actividad **assign** y colóquela en uno de los cuatro triángulos que aparecen cuando la actividad **prompt** está sobre la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="06612-143">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="06612-144">La segunda manera es colocar la actividad **prompt** en el flujo de trabajo en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="06612-144">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="06612-145">A continuación, mantenga el mouse sobre la actividad **assign** y arrastre uno de los rectángulos que aparece hacia abajo hasta la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="06612-145">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="06612-146">Arrastre el mouse para que la línea de conexión de la actividad **assign** se conecte a uno de los rectángulos de la actividad **prompt** y, a continuación, suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="06612-146">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="06612-147">La tercera manera es muy similar a la primera, salvo que en lugar de arrastrar la actividad **prompt** desde el cuadro de **herramientas**, se arrastra desde su ubicación en la superficie de diseño de flujo de trabajo, se mantiene el mouse sobre la actividad **assign** y se coloca en uno de los triángulos que aparece.</span><span class="sxs-lookup"><span data-stu-id="06612-147">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="06612-148">En la **ventana Propiedades** de la actividad **prompt** , escriba `"EnterGuess"` incluir las comillas en el cuadro de valor de la propiedad **BookmarkName** .</span><span class="sxs-lookup"><span data-stu-id="06612-148">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="06612-149">Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="06612-149">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="06612-150">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="06612-150">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="06612-151">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y conéctela con uno de los métodos descritos en el paso anterior para que esté debajo de la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="06612-151">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="06612-152">Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba una expresión de C#**  o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="06612-152">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="06612-153">Arrastre un **FlowDecision** desde la sección **Diagrama de flujo** del cuadro de **herramientas** y conéctelo debajo de la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="06612-153">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="06612-154">En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .</span><span class="sxs-lookup"><span data-stu-id="06612-154">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="06612-155">Arrastre otra actividad **FlowDecision** desde el **cuadro de herramientas** y colóquela debajo de la primera.</span><span class="sxs-lookup"><span data-stu-id="06612-155">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="06612-156">Conecte las dos actividades arrastrando desde el rectángulo con la etiqueta **false** en la actividad **FlowDecision** superior hasta el rectángulo situado en la parte superior de la segunda actividad **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="06612-156">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="06612-157">Si no ve las etiquetas **true** y **false** en el **FlowDecision**, mantenga el mouse sobre el **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="06612-157">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="06612-158">Haga clic en la segunda actividad **FlowDecision** para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="06612-158">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="06612-159">En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .</span><span class="sxs-lookup"><span data-stu-id="06612-159">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="06612-160">Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que estén en paralelo debajo de las dos actividades **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="06612-160">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="06612-161">Conecte la acción **true** de la actividad **FlowDecision** inferior a la actividad **WriteLine** situada más a la izquierda y la acción **false** a la actividad **WriteLine** situada más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="06612-161">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="06612-162">Haga clic en la actividad **WriteLine** situada más a la izquierda para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="06612-162">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="06612-163">Conecte el **WriteLine** en el lado izquierdo de la actividad **prompt** que está por encima de él.</span><span class="sxs-lookup"><span data-stu-id="06612-163">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="06612-164">Haga clic en la actividad **WriteLine** situada más a la derecha para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="06612-164">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="06612-165">Conecte la actividad **WriteLine** al lado derecho de la actividad **prompt** que está sobre ella.</span><span class="sxs-lookup"><span data-stu-id="06612-165">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="06612-166">En el siguiente ejemplo se muestra el flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="06612-166">The following example illustrates the completed workflow.</span></span>  
  
     ![Diagrama que muestra un diagrama de flujo de Windows Workflow Foundation completado.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="06612-168">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-168">To build the workflow</span></span>  
  
1. <span data-ttu-id="06612-169">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="06612-169">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="06612-170">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="06612-170">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="06612-171">Si ya ha completado el paso [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de diagrama de flujo de este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="06612-171">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06612-172">Consulta también</span><span class="sxs-lookup"><span data-stu-id="06612-172">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="06612-173">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="06612-173">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="06612-174">Diseñar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-174">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="06612-175">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="06612-175">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="06612-176">Procedimiento para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="06612-176">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="06612-177">Procedimiento para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06612-177">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
