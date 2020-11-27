---
title: Procedimiento para crear un flujo de trabajo de diagrama de flujo
description: En este artículo se describe la creación de un flujo de trabajo que utiliza las actividades integradas y las actividades personalizadas del artículo anterior.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 185d7aea-68a6-4bd8-adde-45050f33170a
ms.openlocfilehash: f8e0703591629a72e0a8f6eeb05dd9d19c8c4c91
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275832"
---
# <a name="how-to-create-a-flowchart-workflow"></a><span data-ttu-id="cc539-103">Procedimiento para crear un flujo de trabajo de diagrama de flujo</span><span class="sxs-lookup"><span data-stu-id="cc539-103">How to: Create a Flowchart Workflow</span></span>

<span data-ttu-id="cc539-104">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cc539-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="cc539-105">En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.Flowchart> actividad, y las actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="cc539-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.Flowchart> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="cc539-106">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="cc539-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc539-107">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc539-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="cc539-108">Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="cc539-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc539-109">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="cc539-109">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="cc539-110">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-110">To create the workflow</span></span>  
  
1. <span data-ttu-id="cc539-111">Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="cc539-111">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="cc539-112">En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cc539-112">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="cc539-113">Seleccione **Actividad** en la lista **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="cc539-113">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="cc539-114">Escriba `FlowchartNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="cc539-114">Type `FlowchartNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="cc539-115">Arrastre una actividad de **Diagrama de flujo** desde la sección **Diagrama** de flujo del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cc539-115">Drag a **Flowchart** activity from the **Flowchart** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="cc539-116">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-116">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="cc539-117">Haga doble clic en **FlowchartNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="cc539-117">Double-click **FlowchartNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="cc539-118">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="cc539-118">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="cc539-119">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="cc539-119">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="cc539-120">Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="cc539-120">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="cc539-121">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="cc539-121">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="cc539-122">Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `MaxNumber` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="cc539-122">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="cc539-123">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="cc539-123">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="cc539-124">Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="cc539-124">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="cc539-125">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="cc539-125">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="cc539-126">Si no se muestra ningún cuadro **crear variable** , haga clic en la <xref:System.Activities.Statements.Flowchart> actividad en la superficie del diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="cc539-126">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.Flowchart> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="cc539-127">Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="cc539-127">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="cc539-128">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="cc539-128">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="cc539-129">Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="cc539-129">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="cc539-130">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Variables**.</span><span class="sxs-lookup"><span data-stu-id="cc539-130">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="cc539-131">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-131">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="cc539-132">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y mantenga el mouse sobre el nodo **iniciar** , que se encuentra en la parte superior del diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="cc539-132">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and hover it over the **Start** node, which is at the top of the flowchart.</span></span> <span data-ttu-id="cc539-133">Cuando la actividad de **asignación** está sobre el nodo de **Inicio** , aparecen tres triángulos alrededor del nodo de **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="cc539-133">When the **Assign** activity is over the **Start** node, three triangles will appear around the **Start** node.</span></span> <span data-ttu-id="cc539-134">Coloque la actividad **assign** en el triángulo que está justo debajo del nodo de **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="cc539-134">Drop the **Assign** activity on the triangle that is directly below the **Start** node.</span></span> <span data-ttu-id="cc539-135">Se vincularán los dos elementos juntos y se designará la actividad **assign** como la primera actividad del diagrama de flujo.</span><span class="sxs-lookup"><span data-stu-id="cc539-135">This will link the two items together and designates the **Assign** activity as the first activity in the flowchart.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="cc539-136">Las actividades también se pueden indicar como actividad de inicio en el flujo de trabajo si se vinculan manualmente al nodo de inicio.</span><span class="sxs-lookup"><span data-stu-id="cc539-136">Activities can also be indicated as the starting activity in the workflow by manually linking them activity to the start node.</span></span> <span data-ttu-id="cc539-137">Para ello, mantenga el mouse sobre el nodo de **Inicio** , haga clic en uno de los rectángulos que aparecen cuando el mouse está sobre el nodo de **Inicio** y arrastre la línea de conexión hacia abajo hasta la actividad deseada y colóquela en uno de los rectángulos que aparecen.</span><span class="sxs-lookup"><span data-stu-id="cc539-137">To do this, hover the mouse over the **Start** node, click one of the rectangles that appear when the mouse is over the **Start** node, and drag the connecting line down to the desired activity and drop it on one of the rectangles that appear.</span></span> <span data-ttu-id="cc539-138">También puede designar una actividad como la actividad de inicio; para ello, haga clic con el botón secundario en ella y elija **establecer como nodo de inicio**.</span><span class="sxs-lookup"><span data-stu-id="cc539-138">You can also designate an activity as the starting activity by right-clicking the it and choosing **Set as Start Node**.</span></span>  
  
2. <span data-ttu-id="cc539-139">Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="cc539-139">Type `Target` into the **To** box and the following expression into the **Enter a C# Expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="cc539-140">Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="cc539-140">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
3. <span data-ttu-id="cc539-141">Arrastre una actividad **prompt** de la **sección NumberGuessWorkflowActivities** del cuadro de **herramientas**, colóquela debajo de la actividad **assign** del paso anterior y conecte la actividad **prompt** a la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="cc539-141">Drag a **Prompt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox**, drop it below the **Assign** activity from the previous step, and connect the **Prompt** activity to the **Assign** activity.</span></span> <span data-ttu-id="cc539-142">Hay tres maneras de conectar las dos actividades.</span><span class="sxs-lookup"><span data-stu-id="cc539-142">There are three ways to connect the two activities.</span></span> <span data-ttu-id="cc539-143">La primera manera es conectarlas a medida que se coloca la actividad **prompt** en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cc539-143">The first way is to connect them as you drop the **Prompt** activity on the workflow.</span></span> <span data-ttu-id="cc539-144">Cuando arrastre la actividad **prompt** al flujo de trabajo, mantenga el mouse sobre la actividad **assign** y colóquela en uno de los cuatro triángulos que aparecen cuando la actividad **prompt** está sobre la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="cc539-144">As you are dragging the **Prompt** activity to the workflow, hover it over the **Assign** activity and drop it onto one of the four triangles that appear when the **Prompt** activity is over the **Assign** activity.</span></span> <span data-ttu-id="cc539-145">La segunda manera es colocar la actividad **prompt** en el flujo de trabajo en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="cc539-145">The second way is to drop the **Prompt** activity onto the workflow at the desired location.</span></span> <span data-ttu-id="cc539-146">A continuación, mantenga el mouse sobre la actividad **assign** y arrastre uno de los rectángulos que aparece hacia abajo hasta la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="cc539-146">Then, hover the mouse over the **Assign** activity and drag one of the rectangles that appears down to the **Prompt** activity.</span></span> <span data-ttu-id="cc539-147">Arrastre el mouse para que la línea de conexión de la actividad **assign** se conecte a uno de los rectángulos de la actividad **prompt** y, a continuación, suelte el botón del mouse.</span><span class="sxs-lookup"><span data-stu-id="cc539-147">Drag the mouse so that the connecting line from the **Assign** activity connects to one of the rectangles of the **Prompt** activity, and then release the mouse button.</span></span> <span data-ttu-id="cc539-148">La tercera manera es muy similar a la primera, salvo que en lugar de arrastrar la actividad **prompt** desde el cuadro de **herramientas**, se arrastra desde su ubicación en la superficie de diseño de flujo de trabajo, se mantiene el mouse sobre la actividad **assign** y se coloca en uno de los triángulos que aparece.</span><span class="sxs-lookup"><span data-stu-id="cc539-148">The third way is very similar to the first way, except that instead of dragging the **Prompt** activity from the **Toolbox**, you drag it from its location on the workflow design surface, hover it over the **Assign** activity, and drop it onto one of the triangles that appears.</span></span>  
  
4. <span data-ttu-id="cc539-149">En la **ventana Propiedades** de la actividad **prompt** , escriba `"EnterGuess"` incluir las comillas en el cuadro de valor de la propiedad **BookmarkName** .</span><span class="sxs-lookup"><span data-stu-id="cc539-149">In the **Properties Window** for the **Prompt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box.</span></span> <span data-ttu-id="cc539-150">Escriba `Guess` en el cuadro de valor de la propiedad **resultado** y escriba la siguiente expresión en el cuadro de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="cc539-150">Type `Guess` into the **Result** property value box, and type the following expression into the **Text** property box.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="cc539-151">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="cc539-151">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
5. <span data-ttu-id="cc539-152">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y conéctela con uno de los métodos descritos en el paso anterior para que esté debajo de la actividad **prompt** .</span><span class="sxs-lookup"><span data-stu-id="cc539-152">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and connect it using one of the methods described in the previous step so that it is below the **Prompt** activity.</span></span>  
  
6. <span data-ttu-id="cc539-153">Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba una expresión de C#**  o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="cc539-153">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression**  or **Enter a VB expression** box.</span></span>  
  
7. <span data-ttu-id="cc539-154">Arrastre un **FlowDecision** desde la sección **Diagrama de flujo** del cuadro de **herramientas** y conéctelo debajo de la actividad **assign** .</span><span class="sxs-lookup"><span data-stu-id="cc539-154">Drag a **FlowDecision** from the **Flowchart** section of the **Toolbox** and connect it below the **Assign** activity.</span></span> <span data-ttu-id="cc539-155">En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .</span><span class="sxs-lookup"><span data-stu-id="cc539-155">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
8. <span data-ttu-id="cc539-156">Arrastre otra actividad **FlowDecision** desde el **cuadro de herramientas** y colóquela debajo de la primera.</span><span class="sxs-lookup"><span data-stu-id="cc539-156">Drag another **FlowDecision** activity from the **Toolbox** and drop it below the first one.</span></span> <span data-ttu-id="cc539-157">Conecte las dos actividades arrastrando desde el rectángulo con la etiqueta **false** en la actividad **FlowDecision** superior hasta el rectángulo situado en la parte superior de la segunda actividad **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="cc539-157">Connect the two activities by dragging from the rectangle that is labeled **False** on the top **FlowDecision** activity to the rectangle at the top of the second **FlowDecision** activity.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="cc539-158">Si no ve las etiquetas **true** y **false** en el **FlowDecision**, mantenga el mouse sobre el **FlowDecision**.</span><span class="sxs-lookup"><span data-stu-id="cc539-158">If you do not see the **True** and **False** labels on the **FlowDecision**, hover the mouse over the **FlowDecision**.</span></span>  
  
9. <span data-ttu-id="cc539-159">Haga clic en la segunda actividad **FlowDecision** para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="cc539-159">Click the second **FlowDecision** activity to select it.</span></span> <span data-ttu-id="cc539-160">En la **ventana Propiedades**, escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .</span><span class="sxs-lookup"><span data-stu-id="cc539-160">In the **Properties Window**, type the following expression into the **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
10. <span data-ttu-id="cc539-161">Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que estén en paralelo debajo de las dos actividades **FlowDecision** .</span><span class="sxs-lookup"><span data-stu-id="cc539-161">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that they are side by side below the two **FlowDecision** activities.</span></span> <span data-ttu-id="cc539-162">Conecte la acción **true** de la actividad **FlowDecision** inferior a la actividad **WriteLine** situada más a la izquierda y la acción **false** a la actividad **WriteLine** situada más a la derecha.</span><span class="sxs-lookup"><span data-stu-id="cc539-162">Connect the **True** action of the bottom **FlowDecision** activity to the leftmost **WriteLine** activity, and the **False** action to the rightmost **WriteLine** activity.</span></span>  
  
11. <span data-ttu-id="cc539-163">Haga clic en la actividad **WriteLine** situada más a la izquierda para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cc539-163">Click the leftmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
12. <span data-ttu-id="cc539-164">Conecte el **WriteLine** en el lado izquierdo de la actividad **prompt** que está por encima de él.</span><span class="sxs-lookup"><span data-stu-id="cc539-164">Connect the **WriteLine** to the left side of the **Prompt** activity that is above it.</span></span>  
  
13. <span data-ttu-id="cc539-165">Haga clic en la actividad **WriteLine** situada más a la derecha para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** en la **ventana Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="cc539-165">Click the rightmost **WriteLine** activity to select it, and type the following expression into the **Text** property value box in the **Properties Window**.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
14. <span data-ttu-id="cc539-166">Conecte la actividad **WriteLine** al lado derecho de la actividad **prompt** que está sobre ella.</span><span class="sxs-lookup"><span data-stu-id="cc539-166">Connect the **WriteLine** activity to the right side of the **Prompt** activity above it.</span></span>  
  
     <span data-ttu-id="cc539-167">En el siguiente ejemplo se muestra el flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="cc539-167">The following example illustrates the completed workflow.</span></span>  
  
     ![Diagrama que muestra un diagrama de flujo de Windows Workflow Foundation completado.](./media/how-to-create-a-flowchart-workflow/completed-windows-workflow-flowchart.png)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="cc539-169">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-169">To build the workflow</span></span>  
  
1. <span data-ttu-id="cc539-170">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="cc539-170">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="cc539-171">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cc539-171">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="cc539-172">Si ya ha completado el paso [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de diagrama de flujo de este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="cc539-172">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the flowchart workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc539-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc539-173">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="cc539-174">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="cc539-174">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="cc539-175">Diseñar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-175">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="cc539-176">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="cc539-176">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="cc539-177">Procedimiento para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="cc539-177">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="cc539-178">Procedimiento para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc539-178">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
