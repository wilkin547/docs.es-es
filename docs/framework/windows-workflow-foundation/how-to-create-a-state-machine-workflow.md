---
title: Procedimiento para crear un flujo de trabajo de máquina de estados
description: En este artículo se crea un flujo de trabajo que utiliza las actividades integradas, como la actividad StateMachine, y las actividades personalizadas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3ec60e8f-fad4-493e-a426-e7962d7aee8c
ms.openlocfilehash: 8e977a182d55143f8d877d61a0f0345bbe6bded4
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190473"
---
# <a name="how-to-create-a-state-machine-workflow"></a><span data-ttu-id="3f197-103">Procedimiento para crear un flujo de trabajo de máquina de estados</span><span class="sxs-lookup"><span data-stu-id="3f197-103">How to: Create a State Machine Workflow</span></span>

<span data-ttu-id="3f197-104">Se pueden construir flujos de trabajo a partir de actividades integradas, así como de actividades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3f197-104">Workflows can be constructed from built-in activities as well as from custom activities.</span></span> <span data-ttu-id="3f197-105">En este tema se describe cómo crear un flujo de trabajo que usa tanto actividades integradas, como la <xref:System.Activities.Statements.StateMachine> actividad, y las actividades personalizadas del tema [Cómo: crear una actividad](how-to-create-an-activity.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="3f197-105">This topic steps through creating a workflow that uses both built-in activities such as the <xref:System.Activities.Statements.StateMachine> activity, and the custom activities from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic.</span></span> <span data-ttu-id="3f197-106">El flujo de trabajo modela un juego de adivinanzas de números.</span><span class="sxs-lookup"><span data-stu-id="3f197-106">The workflow models a number guessing game.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3f197-107">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="3f197-107">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="3f197-108">Para completar este tema, primero debe completar [Cómo: crear una actividad](how-to-create-an-activity.md).</span><span class="sxs-lookup"><span data-stu-id="3f197-108">To complete this topic, you must first complete [How to: Create an Activity](how-to-create-an-activity.md).</span></span>  
  
### <a name="to-create-the-workflow"></a><span data-ttu-id="3f197-109">Para crear el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-109">To create the workflow</span></span>  
  
1. <span data-ttu-id="3f197-110">Haga clic con el botón secundario en **NumberGuessWorkflowActivities** en **Explorador de soluciones** y seleccione **Agregar**, **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="3f197-110">Right-click **NumberGuessWorkflowActivities** in **Solution Explorer** and select **Add**, **New Item**.</span></span>  
  
2. <span data-ttu-id="3f197-111">En el nodo **instalado**, **elementos comunes** , seleccione **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="3f197-111">In the **Installed**, **Common Items** node, select **Workflow**.</span></span> <span data-ttu-id="3f197-112">Seleccione **Actividad** en la lista **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="3f197-112">Select **Activity** from the **Workflow** list.</span></span>  
  
3. <span data-ttu-id="3f197-113">Escriba `StateMachineNumberGuessWorkflow` en el cuadro **nombre** y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3f197-113">Type `StateMachineNumberGuessWorkflow` into the **Name** box and click **Add**.</span></span>  
  
4. <span data-ttu-id="3f197-114">Arrastre una actividad **StateMachine** desde la sección **máquina de Estados** del **cuadro de herramientas** y colóquela en la etiqueta **colocar actividad aquí** en la superficie de diseño de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f197-114">Drag a **StateMachine** activity from the **State Machine** section of the **Toolbox** and drop it onto the **Drop activity here** label on the workflow design surface.</span></span>  
  
### <a name="to-create-the-workflow-variables-and-arguments"></a><span data-ttu-id="3f197-115">Para crear las variables y argumentos de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-115">To create the workflow variables and arguments</span></span>  
  
1. <span data-ttu-id="3f197-116">Haga doble clic en **StateMachineNumberGuessWorkflow. Xaml** en **Explorador de soluciones** para mostrar el flujo de trabajo en el diseñador, si aún no se muestra.</span><span class="sxs-lookup"><span data-stu-id="3f197-116">Double-click **StateMachineNumberGuessWorkflow.xaml** in **Solution Explorer** to display the workflow in the designer, if it is not already displayed.</span></span>  
  
2. <span data-ttu-id="3f197-117">Haga clic en **argumentos** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **argumentos** .</span><span class="sxs-lookup"><span data-stu-id="3f197-117">Click **Arguments** in the lower-left side of the workflow designer to display the **Arguments** pane.</span></span>  
  
3. <span data-ttu-id="3f197-118">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="3f197-118">Click **Create Argument**.</span></span>  
  
4. <span data-ttu-id="3f197-119">Escriba `MaxNumber` en el cuadro **nombre** , seleccione **en en** la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar para guardar el argumento.</span><span class="sxs-lookup"><span data-stu-id="3f197-119">Type `MaxNumber` into the **Name** box, select **In** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER to save the argument.</span></span>  
  
5. <span data-ttu-id="3f197-120">Haga clic en **Crear argumento**.</span><span class="sxs-lookup"><span data-stu-id="3f197-120">Click **Create Argument**.</span></span>  
  
6. <span data-ttu-id="3f197-121">Escriba `Turns` en el cuadro **nombre** que se encuentra debajo del argumento recién agregado `MaxNumber` , seleccione **salida** en la lista desplegable **Dirección** , seleccione **Int32** en la lista desplegable **tipo de argumento** y, a continuación, presione Entrar.</span><span class="sxs-lookup"><span data-stu-id="3f197-121">Type `Turns` into the **Name** box that is below the newly added `MaxNumber` argument, select **Out** from the **Direction** drop-down list, select **Int32** from the **Argument type** drop-down list, and then press ENTER.</span></span>  
  
7. <span data-ttu-id="3f197-122">Haga clic en **Argumentos** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Argumentos**.</span><span class="sxs-lookup"><span data-stu-id="3f197-122">Click **Arguments** in the lower-left side of the activity designer to close the **Arguments** pane.</span></span>  
  
8. <span data-ttu-id="3f197-123">Haga clic en **variables** en el lado inferior izquierdo del diseñador de flujo de trabajo para mostrar el panel **variables** .</span><span class="sxs-lookup"><span data-stu-id="3f197-123">Click **Variables** in the lower-left side of the workflow designer to display the **Variables** pane.</span></span>  
  
9. <span data-ttu-id="3f197-124">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="3f197-124">Click **Create Variable**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="3f197-125">Si no se muestra ningún cuadro **crear variable** , haga clic en la <xref:System.Activities.Statements.StateMachine> actividad en la superficie del diseñador de flujo de trabajo para seleccionarla.</span><span class="sxs-lookup"><span data-stu-id="3f197-125">If no **Create Variable** box is displayed, click the <xref:System.Activities.Statements.StateMachine> activity on the workflow designer surface to select it.</span></span>  
  
10. <span data-ttu-id="3f197-126">Escriba `Guess` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="3f197-126">Type `Guess` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
11. <span data-ttu-id="3f197-127">Haga clic en **Crear variable**.</span><span class="sxs-lookup"><span data-stu-id="3f197-127">Click **Create Variable**.</span></span>  
  
12. <span data-ttu-id="3f197-128">Escriba `Target` en el cuadro **nombre** , seleccione **Int32** en la lista desplegable **tipo de variable** y presione Entrar para guardar la variable.</span><span class="sxs-lookup"><span data-stu-id="3f197-128">Type `Target` into the **Name** box, select **Int32** from the **Variable type** drop-down list, and then press ENTER to save the variable.</span></span>  
  
13. <span data-ttu-id="3f197-129">Haga clic en **Variables** en el lado inferior izquierdo del Diseñador de actividad para cerrar el panel **Variables**.</span><span class="sxs-lookup"><span data-stu-id="3f197-129">Click **Variables** in the lower-left side of the activity designer to close the **Variables** pane.</span></span>  
  
### <a name="to-add-the-workflow-activities"></a><span data-ttu-id="3f197-130">Para agregar actividades de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-130">To add the workflow activities</span></span>  
  
1. <span data-ttu-id="3f197-131">Haga clic en **State1** para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="3f197-131">Click **State1** to select it.</span></span> <span data-ttu-id="3f197-132">En la **ventana Propiedades**, cambie **displayName** a `Initialize Target` .</span><span class="sxs-lookup"><span data-stu-id="3f197-132">In the **Properties Window**, change the **DisplayName** to `Initialize Target`.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="3f197-133">Si no se muestra la **ventana Propiedades** , seleccione **ventana Propiedades** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="3f197-133">If the **Properties Window** is not displayed, select **Properties Window** from the **View** menu.</span></span>  
  
2. <span data-ttu-id="3f197-134">Haga doble clic en el estado de **destino Initialize** recién cambiado en el diseñador de flujo de trabajo para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="3f197-134">Double-click the newly renamed **Initialize Target** state in the workflow designer to expand it.</span></span>  
  
3. <span data-ttu-id="3f197-135">Arrastre una actividad **assign** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección **entrada** del estado.</span><span class="sxs-lookup"><span data-stu-id="3f197-135">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span> <span data-ttu-id="3f197-136">Escriba `Target` en el cuadro **para** y la siguiente expresión en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="3f197-136">Type `Target` into the **To** box and the following expression into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
    ```vb  
    New System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    ```csharp  
    new System.Random().Next(1, MaxNumber + 1)  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="3f197-137">Si no está visible la ventana **Cuadro de herramientas**, seleccione **Cuadro de herramientas** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="3f197-137">If the **Toolbox** window is not displayed, select **Toolbox** from the **View** menu.</span></span>  
  
4. <span data-ttu-id="3f197-138">Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f197-138">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
5. <span data-ttu-id="3f197-139">Arrastre una actividad **State** desde la sección **máquina de Estados** del **cuadro de herramientas** hasta el diseñador de flujo de trabajo y mantenga el mouse sobre el estado de **inicialización de destino** .</span><span class="sxs-lookup"><span data-stu-id="3f197-139">Drag a **State** activity from the **State Machine** section of the **Toolbox** onto the workflow designer and hover it over the **Initialize Target** state.</span></span> <span data-ttu-id="3f197-140">Tenga en cuenta que se mostrarán cuatro triángulos alrededor del estado de **destino de inicialización** cuando el nuevo estado se sitúa sobre él.</span><span class="sxs-lookup"><span data-stu-id="3f197-140">Note that four triangles will appear around the **Initialize Target** state when the new state is over it.</span></span> <span data-ttu-id="3f197-141">Quite el nuevo estado del triángulo que está inmediatamente por debajo del estado de **inicialización de destino** .</span><span class="sxs-lookup"><span data-stu-id="3f197-141">Drop the new state on the triangle that is immediately below the **Initialize Target** state.</span></span> <span data-ttu-id="3f197-142">Esto coloca el nuevo estado en el flujo de trabajo y crea una transición desde el estado de **destino Initialize** al nuevo estado.</span><span class="sxs-lookup"><span data-stu-id="3f197-142">This places the new state onto the workflow and creates a transition from the **Initialize Target** state to the new state.</span></span>  
  
6. <span data-ttu-id="3f197-143">Haga clic en **State1** para seleccionarlo, cambie **displayName** a y, a continuación, haga `Enter Guess` doble clic en el estado en el diseñador de flujo de trabajo para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="3f197-143">Click **State1** to select it, change the **DisplayName** to `Enter Guess`, and then double-click the state in the workflow designer to expand it.</span></span>  
  
7. <span data-ttu-id="3f197-144">Arrastre una actividad **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección **entrada** del estado.</span><span class="sxs-lookup"><span data-stu-id="3f197-144">Drag a **WriteLine** activity from the **Primitives** section of the **Toolbox** and drop it onto the **Entry** section of the state.</span></span>  
  
8. <span data-ttu-id="3f197-145">Escriba la siguiente expresión en el cuadro de propiedad **texto** de **WriteLine**.</span><span class="sxs-lookup"><span data-stu-id="3f197-145">Type the following expression into the **Text** property box of the **WriteLine**.</span></span>  
  
    ```vb  
    "Please enter a number between 1 and " & MaxNumber  
    ```  
  
    ```csharp  
    "Please enter a number between 1 and " + MaxNumber  
    ```  
  
9. <span data-ttu-id="3f197-146">Arrastre una actividad **assign** desde la sección **primitivas** del **cuadro de herramientas** y colóquela en la sección de **salida** del estado.</span><span class="sxs-lookup"><span data-stu-id="3f197-146">Drag an **Assign** activity from the **Primitives** section of the **Toolbox** and drop onto the **Exit** section of the state.</span></span>  
  
10. <span data-ttu-id="3f197-147">Escriba `Turns` en el cuadro **para** y `Turns + 1` en el cuadro **Escriba una expresión de C#** o **Escriba una expresión de VB** .</span><span class="sxs-lookup"><span data-stu-id="3f197-147">Type `Turns` into the **To** box and `Turns + 1` into the **Enter a C# expression** or **Enter a VB expression** box.</span></span>  
  
11. <span data-ttu-id="3f197-148">Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f197-148">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
12. <span data-ttu-id="3f197-149">Arrastre una actividad **FinalState** desde la sección **máquina de Estados** del **cuadro de herramientas**, mantenga el mouse sobre el estado **Enter Guess** y colóquela en el triángulo que aparece a la derecha del estado **Enter Guess** para que se cree una transición entre **Enter Guess** y **FinalState**.</span><span class="sxs-lookup"><span data-stu-id="3f197-149">Drag a **FinalState** activity from the **State Machine** section of the **Toolbox**, hover it over the **Enter Guess** state, and drop it onto the triangle that appears to the right of the **Enter Guess** state so that a transition is created between **Enter Guess** and **FinalState**.</span></span>  
  
13. <span data-ttu-id="3f197-150">El nombre predeterminado de la transición es **T2**.</span><span class="sxs-lookup"><span data-stu-id="3f197-150">The default name of the transition is **T2**.</span></span> <span data-ttu-id="3f197-151">Haga clic en la transición en el diseñador de flujo de trabajo para seleccionarla y establezca su **displayName** en **Guess correct**.</span><span class="sxs-lookup"><span data-stu-id="3f197-151">Click the transition in the workflow designer to select it, and set its **DisplayName** to **Guess Correct**.</span></span> <span data-ttu-id="3f197-152">Después, haga clic en el **FinalState** y selecciónelo y arrástrelo hacia la derecha para que haya espacio para que se muestre el nombre completo de la transición sin superposición de ninguno de los dos Estados.</span><span class="sxs-lookup"><span data-stu-id="3f197-152">Then click and select the **FinalState**, and drag it to the right so that there is room for the full transition name to be displayed without overlaying either of the two states.</span></span> <span data-ttu-id="3f197-153">Así resultará más fácil completar los pasos restantes del tutorial.</span><span class="sxs-lookup"><span data-stu-id="3f197-153">This will make it easier to complete the remaining steps in the tutorial.</span></span>  
  
14. <span data-ttu-id="3f197-154">Haga doble clic en la transición **Guess correct** con el nuevo nombre en el diseñador de flujo de trabajo para expandirla.</span><span class="sxs-lookup"><span data-stu-id="3f197-154">Double-click the newly renamed **Guess Correct** transition in the workflow designer to expand it.</span></span>  
  
15. <span data-ttu-id="3f197-155">Arrastre una actividad **ReadInt** desde la sección **NumberGuessWorkflowActivities** del **cuadro de herramientas** y colóquela en la sección **desencadenador** de la transición.</span><span class="sxs-lookup"><span data-stu-id="3f197-155">Drag a **ReadInt** activity from the **NumberGuessWorkflowActivities** section of the **Toolbox** and drop it in the **Trigger** section of the transition.</span></span>  
  
16. <span data-ttu-id="3f197-156">En la **ventana Propiedades** de la actividad **ReadInt** , escriba `"EnterGuess"` entre comillas en el cuadro de valor de la propiedad **BookmarkName** y escriba `Guess` en el cuadro de valor de la propiedad **resultado** .</span><span class="sxs-lookup"><span data-stu-id="3f197-156">In the **Properties Window** for the **ReadInt** activity, type `"EnterGuess"` including the quotes into the **BookmarkName** property value box, and type `Guess` into the **Result** property value box</span></span>  
  
17. <span data-ttu-id="3f197-157">Escriba la siguiente expresión en el cuadro de valor de la propiedad de **condición** **adivinar** la transición correcta.</span><span class="sxs-lookup"><span data-stu-id="3f197-157">Type the following expression into the **Guess Correct** transition’s **Condition** property value box.</span></span>  
  
    ```vb  
    Guess = Target  
    ```  
  
    ```csharp  
    Guess == Target  
    ```  
  
18. <span data-ttu-id="3f197-158">Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f197-158">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3f197-159">Una transición se produce cuando se recibe el evento desencadenador y <xref:System.Activities.Statements.Transition.Condition%2A>, si está presente, se evalúa como `True`.</span><span class="sxs-lookup"><span data-stu-id="3f197-159">A transition occurs when the trigger event is received and the <xref:System.Activities.Statements.Transition.Condition%2A>, if present, evaluates to `True`.</span></span> <span data-ttu-id="3f197-160">En esta transición, si el usuario `Guess` coincide con el generado aleatoriamente `Target` , el control pasa a **FinalState** y el flujo de trabajo se completa.</span><span class="sxs-lookup"><span data-stu-id="3f197-160">For this transition, if the user’s `Guess` matches the randomly generated `Target`, then control passes to the **FinalState** and the workflow completes.</span></span>  
  
19. <span data-ttu-id="3f197-161">Dependiendo de si la estimación es correcta, el flujo de trabajo debe realizar la transición a **FinalState** o al estado **Enter Guess** para otro intento.</span><span class="sxs-lookup"><span data-stu-id="3f197-161">Depending on whether the guess is correct, the workflow should transition either to the **FinalState** or back to the **Enter Guess** state for another try.</span></span> <span data-ttu-id="3f197-162">Ambas transiciones comparten el mismo desencadenador de espera para que la estimación del usuario se reciba a través de la actividad **ReadInt** .</span><span class="sxs-lookup"><span data-stu-id="3f197-162">Both transitions share the same trigger of waiting for the user’s guess to be received via the **ReadInt** activity.</span></span> <span data-ttu-id="3f197-163">Esto se denomina una transición compartida.</span><span class="sxs-lookup"><span data-stu-id="3f197-163">This is called a shared transition.</span></span> <span data-ttu-id="3f197-164">Para crear una transición compartida, haga clic en el círculo que indica el inicio de la transición **Guess correct** y arrástrela hasta el estado deseado.</span><span class="sxs-lookup"><span data-stu-id="3f197-164">To create a shared transition, click the circle that indicates the start of the **Guess Correct** transition and drag it to the desired state.</span></span> <span data-ttu-id="3f197-165">En este caso, la transición es una transición automática, por lo que debe arrastrar el punto inicial de la transición **Guess correct** y colocarla de nuevo en la parte inferior del estado **Enter Guess** .</span><span class="sxs-lookup"><span data-stu-id="3f197-165">In this case the transition is a self-transition, so drag the start point of the **Guess Correct** transition and drop it back onto the bottom of the **Enter Guess** state.</span></span> <span data-ttu-id="3f197-166">Después de crear la transición, selecciónela en el diseñador de flujo de trabajo y establezca su propiedad **displayName** en **Guess Incorrect**.</span><span class="sxs-lookup"><span data-stu-id="3f197-166">After creating the transition, select it in the workflow designer and set its **DisplayName** property to **Guess Incorrect**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3f197-167">Las transiciones compartidas también se pueden crear desde el diseñador de transición haciendo clic en **Agregar transición de desencadenador compartido** en la parte inferior del diseñador de transición y, a continuación, seleccionando el estado de destino deseado en la lista desplegable **Estados disponibles para conectar** .</span><span class="sxs-lookup"><span data-stu-id="3f197-167">Shared transitions can also be created from within the transition designer by clicking **Add shared trigger transition** at the bottom of the transition designer, and then selecting the desired target state from the **Available states to connect** drop-down.</span></span>  
    > [!NOTE]
    > <span data-ttu-id="3f197-168">Tenga en cuenta que si la condición <xref:System.Activities.Statements.Transition.Condition%2A> de una transición se evalúa en `false` (o todas las condiciones de una transición de desencadenador compartido se evalúan en `false`), la transición no se producirá y se reprogramarán todos los desencadenadores para todas las transiciones desde el estado.</span><span class="sxs-lookup"><span data-stu-id="3f197-168">Note that if the <xref:System.Activities.Statements.Transition.Condition%2A> of a transition evaluates to `false` (or all of the conditions of a shared trigger transition evaluate to `false`), the transition will not occur and all triggers for all the transitions from the state will be rescheduled.</span></span> <span data-ttu-id="3f197-169">En este tutorial, no puede suceder esta situación debido a la forma en que están configuradas las condiciones (tenemos acciones específicas para determinar si el supuesto es correcto o incorrecto).</span><span class="sxs-lookup"><span data-stu-id="3f197-169">In this tutorial, this situation cannot happen because of the way the conditions are configured (we have specific actions for whether the guess is correct or incorrect).</span></span>  
  
20. <span data-ttu-id="3f197-170">Haga doble clic en la transición **adivinar incorrectamente** en el diseñador de flujo de trabajo para expandirla.</span><span class="sxs-lookup"><span data-stu-id="3f197-170">Double-click the **Guess Incorrect** transition in the workflow designer to expand it.</span></span> <span data-ttu-id="3f197-171">Tenga en cuenta que el **desencadenador** ya está establecido en la misma actividad **ReadInt** usada por la transición **Guess correct** .</span><span class="sxs-lookup"><span data-stu-id="3f197-171">Note that the **Trigger** is already set to the same **ReadInt** activity that was used by the **Guess Correct** transition.</span></span>  
  
21. <span data-ttu-id="3f197-172">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** .</span><span class="sxs-lookup"><span data-stu-id="3f197-172">Type the following expression into the **Condition** property value box.</span></span>  
  
    ```vb  
    Guess <> Target  
    ```  
  
    ```csharp  
    Guess != Target  
    ```  
  
22. <span data-ttu-id="3f197-173">Arrastre una actividad **If** de la sección **flujo de control** del **cuadro de herramientas** y colóquela en la sección **acción** de la transición.</span><span class="sxs-lookup"><span data-stu-id="3f197-173">Drag an **If** activity from the **Control Flow** section of the **Toolbox** and drop it in the **Action** section of the transition.</span></span>  
  
23. <span data-ttu-id="3f197-174">Escriba la siguiente expresión en el cuadro de valor de la propiedad **condición** de la actividad **If** .</span><span class="sxs-lookup"><span data-stu-id="3f197-174">Type the following expression into the **If** activity’s **Condition** property value box.</span></span>  
  
    ```text
    Guess < Target
    ```  
  
24. <span data-ttu-id="3f197-175">Arrastre dos actividades **WriteLine** de la sección **primitivas** del **cuadro de herramientas** y colóquelas de modo que una esté en la sección **then** de la actividad **If** y otra esté en la sección **else** .</span><span class="sxs-lookup"><span data-stu-id="3f197-175">Drag two **WriteLine** activities from the **Primitives** section of the **Toolbox** and drop them so that one is in the **Then** section of the **If** activity, and one is in the **Else** section.</span></span>  
  
25. <span data-ttu-id="3f197-176">Haga clic en la actividad **WriteLine** en la sección **then** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **Text** .</span><span class="sxs-lookup"><span data-stu-id="3f197-176">Click the **WriteLine** activity in the **Then** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too low."  
    ```  
  
26. <span data-ttu-id="3f197-177">Haga clic en la actividad **WriteLine** en la sección **otro** para seleccionarla y escriba la siguiente expresión en el cuadro de valor de la propiedad **texto** .</span><span class="sxs-lookup"><span data-stu-id="3f197-177">Click the **WriteLine** activity in the **Else** section to select it, and type the following expression into the **Text** property value box.</span></span>  
  
    ```text
    "Your guess is too high."  
    ```  
  
27. <span data-ttu-id="3f197-178">Vuelva a la vista de equipo de estado general en el diseñador de flujo de trabajo haciendo clic en **StateMachine** en la pantalla de la ruta de navegación en la parte superior del diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3f197-178">Return to the overall state machine view in the workflow designer by clicking **StateMachine** in the breadcrumb display at the top of the workflow designer.</span></span>  
  
     <span data-ttu-id="3f197-179">En el siguiente ejemplo se muestra el flujo de trabajo completado.</span><span class="sxs-lookup"><span data-stu-id="3f197-179">The following example illustrates the completed workflow.</span></span>  
  
     ![Ilustración que muestra el flujo de trabajo de equipo de estado completado.](./media/how-to-create-a-state-machine-workflow/complete-state-machine-workflow.jpg)  
  
### <a name="to-build-the-workflow"></a><span data-ttu-id="3f197-181">Para compilar el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-181">To build the workflow</span></span>  
  
1. <span data-ttu-id="3f197-182">Presione CTRL+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="3f197-182">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
     <span data-ttu-id="3f197-183">Para obtener instrucciones sobre cómo ejecutar el flujo de trabajo, vea el tema siguiente, [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3f197-183">For instructions on how to run the workflow, please see the next topic, [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span> <span data-ttu-id="3f197-184">Si ya ha completado el paso [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md) con un estilo diferente de flujo de trabajo y desea ejecutarlo mediante el flujo de trabajo de máquina de Estados desde este paso, vaya a la sección [para compilar y ejecutar la aplicación](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) de [Cómo: ejecutar un flujo de trabajo](how-to-run-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3f197-184">If you have already completed the [How to: Run a Workflow](how-to-run-a-workflow.md) step with a different style of workflow and wish to run it using the state machine workflow from this step, skip ahead to the [To build and run the application](how-to-run-a-workflow.md#BKMK_ToRunTheApplication) section of [How to: Run a Workflow](how-to-run-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f197-185">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3f197-185">See also</span></span>

- <xref:System.Activities.Statements.Flowchart>
- <xref:System.Activities.Statements.FlowDecision>
- [<span data-ttu-id="3f197-186">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="3f197-186">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="3f197-187">Diseñar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-187">Designing Workflows</span></span>](designing-workflows.md)
- [<span data-ttu-id="3f197-188">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="3f197-188">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="3f197-189">Procedimiento para crear una actividad</span><span class="sxs-lookup"><span data-stu-id="3f197-189">How to: Create an Activity</span></span>](how-to-create-an-activity.md)
- [<span data-ttu-id="3f197-190">Procedimiento para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f197-190">How to: Run a Workflow</span></span>](how-to-run-a-workflow.md)
