---
title: Procedimiento para ejecutar un flujo de trabajo
description: En este artículo se muestra cómo crear un host de flujo de trabajo y ejecutar el flujo de trabajo definido en un artículo anterior en esta Windows Workflow Foundation serie de tutoriales.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 7f76ed5ad1a76a155489339a9febf12eefd64ae8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279992"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="537d2-103">Procedimiento para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-103">How to: Run a Workflow</span></span>

<span data-ttu-id="537d2-104">Este tema es una continuación del tutorial introductorio de Windows Workflow Foundation y explica cómo crear un host de flujo de trabajo y ejecutar el flujo de trabajo definido en el tema [How to: Create a Workflow](how-to-create-a-workflow.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="537d2-104">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="537d2-105">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="537d2-105">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="537d2-106">Para completar este tema, primero debe finalizar [How to: Create an Activity](how-to-create-an-activity.md) y [How to: Create a Workflow](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="537d2-106">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
> <span data-ttu-id="537d2-107">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="537d2-107">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="537d2-108">Para crear el proyecto de host de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-108">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="537d2-109">Abra la solución del tema anterior [Cómo: crear una actividad](how-to-create-an-activity.md) mediante Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="537d2-109">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="537d2-110">Haga clic con el botón secundario en la solución **WF45GettingStartedTutorial** en el **Explorador de soluciones** y seleccione **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="537d2-110">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    > <span data-ttu-id="537d2-111">Si no está visible la ventana **Explorador de soluciones**, seleccione **Explorador de soluciones** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="537d2-111">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="537d2-112">En el nodo **Instalado** , seleccione **Visual C#**, **Flujo de trabajo** (o **Visual Basic**, **Flujo de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="537d2-112">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    > <span data-ttu-id="537d2-113">En función del lenguaje de programación configurado como lenguaje principal en Visual Studio, es posible que el nodo **Visual C#** o **Visual Basic** se encuentre debajo del nodo **Otros lenguajes** del nodo **Instalados**.</span><span class="sxs-lookup"><span data-stu-id="537d2-113">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="537d2-114">Asegúrese de que **.NET Framework 4.5** está seleccionado en la lista desplegable de versiones de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="537d2-114">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="537d2-115">Seleccione **Aplicación de consola de flujos de trabajo** en la lista **Flujo de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="537d2-115">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="537d2-116">Escriba `NumberGuessWorkflowHost` en el cuadro **Nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="537d2-116">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="537d2-117">Así se crea una aplicación de flujo de trabajo de inicio con soporte básico de hospedaje de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-117">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="537d2-118">Este código de hospedaje básico se modifica y se usa para ejecutar la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-118">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="537d2-119">Haga clic con el botón secundario en el proyecto **NumberGuessWorkflowHost** recién agregado en el **Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="537d2-119">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="537d2-120">Seleccione **Solución** en la lista **Agregar referencia** , marque la casilla junto **NumberGuessWorkflowActivities** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="537d2-120">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="537d2-121">Haga clic con el botón secundario en **Workflow1.xaml** en el **Explorador de soluciones** y elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="537d2-121">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="537d2-122">Haga clic en **ACEPTAR** para continuar.</span><span class="sxs-lookup"><span data-stu-id="537d2-122">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="537d2-123">Para modificar el código de hospedaje de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-123">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="537d2-124">Haga doble clic en **Program.cs** o en **Module1.vb** en el **Explorador de soluciones** para mostrar el código.</span><span class="sxs-lookup"><span data-stu-id="537d2-124">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    > <span data-ttu-id="537d2-125">Si no está visible la ventana **Explorador de soluciones**, seleccione **Explorador de soluciones** en el menú **Ver**.</span><span class="sxs-lookup"><span data-stu-id="537d2-125">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="537d2-126">Dado que este proyecto se creó con la plantilla **Aplicación de consola de flujos de trabajo** , **Program.cs** o **Module1.vb** , contiene el siguiente código básico de hospedaje de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-126">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition.
    Dim workflow1 As Activity = New Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition.
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="537d2-127">Este código de hospedaje generado usa <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="537d2-127">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="537d2-128"><xref:System.Activities.WorkflowInvoker> proporciona una manera sencilla de invocar un flujo de trabajo como si fuera una llamada al método y se puede usar solo para los flujos de trabajo que no usan la persistencia.</span><span class="sxs-lookup"><span data-stu-id="537d2-128"><xref:System.Activities.WorkflowInvoker> provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <span data-ttu-id="537d2-129"><xref:System.Activities.WorkflowApplication> proporciona un modelo más enriquecido para ejecutar flujos de trabajo que incluye notificación de eventos de ciclo de vida, control de ejecución, reanudación de marcadores y persistencia.</span><span class="sxs-lookup"><span data-stu-id="537d2-129"><xref:System.Activities.WorkflowApplication> provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="537d2-130">Este ejemplo usa marcadores y <xref:System.Activities.WorkflowApplication> se usa para hospedar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-130">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="537d2-131">Agregue la siguiente instrucción `using` o **Imports** al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones **using** o **Imports** existentes.</span><span class="sxs-lookup"><span data-stu-id="537d2-131">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="537d2-132">Reemplace las líneas de código que usan <xref:System.Activities.WorkflowInvoker> por el siguiente código básico de hospedaje <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="537d2-132">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="537d2-133">Este código de hospedaje de ejemplo muestra los pasos básicos para hospedar e invocar un flujo de trabajo, pero no contiene, sin embargo, la funcionalidad necesaria para ejecutar correctamente el flujo de trabajo en este tema.</span><span class="sxs-lookup"><span data-stu-id="537d2-133">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="537d2-134">En los pasos que figuran a continuación, el código básico se modifica y se agregan características adicionales hasta completar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="537d2-134">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="537d2-135">Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="537d2-135">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="537d2-136">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-136">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="537d2-137">Este código crea un objeto <xref:System.Activities.WorkflowApplication>, se suscribe a tres eventos de ciclo de vida de flujo de trabajo, inicia el flujo de trabajo con una llamada a <xref:System.Activities.WorkflowApplication.Run%2A>y espera a que el flujo de trabajo se complete.</span><span class="sxs-lookup"><span data-stu-id="537d2-137">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="537d2-138">Cuando el flujo de trabajo finaliza, se establece <xref:System.Threading.AutoResetEvent> y se completa la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="537d2-138">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="537d2-139">Para definir argumentos de entrada de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-139">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="537d2-140">Agregue la siguiente instrucción al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones `using` o `Imports` existentes.</span><span class="sxs-lookup"><span data-stu-id="537d2-140">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="537d2-141">Reemplace la línea de código que crea el nuevo <xref:System.Activities.WorkflowApplication> con el siguiente código que crea y pasa un diccionario de parámetros al flujo de trabajo cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="537d2-141">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="537d2-142">Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="537d2-142">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="537d2-143">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-143">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="537d2-144">Este diccionario contiene un elemento con una clave de `MaxNumber`.</span><span class="sxs-lookup"><span data-stu-id="537d2-144">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="537d2-145">Las claves del diccionario de entrada corresponden a argumentos de entrada en la actividad raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-145">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> <span data-ttu-id="537d2-146">El flujo de trabajo usa`MaxNumber` para determinar el límite superior para el número generado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="537d2-146">`MaxNumber` is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="537d2-147">Para recuperar parámetros de salida de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-147">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="537d2-148">Modifique el controlador <xref:System.Activities.WorkflowApplication.Completed%2A> para recuperar y mostrar el número de intentos que usó el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-148">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="537d2-149">Para reanudar un marcador</span><span class="sxs-lookup"><span data-stu-id="537d2-149">To resume a bookmark</span></span>

1. <span data-ttu-id="537d2-150">Agregue el siguiente código en la parte superior del método `Main` justo después de la declaración <xref:System.Threading.AutoResetEvent> existente.</span><span class="sxs-lookup"><span data-stu-id="537d2-150">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="537d2-151">Agregue el siguiente controlador <xref:System.Activities.WorkflowApplication.Idle%2A> justo después de los tres controladores de ciclo de vida de flujo de trabajo existentes en `Main`.</span><span class="sxs-lookup"><span data-stu-id="537d2-151">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="537d2-152">Cada vez que el flujo de trabajo se vuelve inactivo a la espera de la siguiente estimación, se llama a este controlador y `idleAction` <xref:System.Threading.AutoResetEvent> se establece.</span><span class="sxs-lookup"><span data-stu-id="537d2-152">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="537d2-153">El código en el siguiente paso usa `idleEvent` y `syncEvent` para determinar si el flujo de trabajo está esperando la siguiente suposición o si se ha completado.</span><span class="sxs-lookup"><span data-stu-id="537d2-153">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    > <span data-ttu-id="537d2-154">En este ejemplo, la aplicación host usa eventos de restablecimiento automático en los controladores <xref:System.Activities.WorkflowApplication.Completed%2A> y <xref:System.Activities.WorkflowApplication.Idle%2A> para sincronizar la aplicación host con el progreso del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-154">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="537d2-155">No es necesario bloquear y esperar a que el flujo de trabajo se vuelva inactivo para reanudar un marcador, aunque en este ejemplo los eventos de sincronización resultan necesarios para que el host sepa si se ha completado el flujo de trabajo o si está esperando más entradas de usuario mediante <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="537d2-155">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="537d2-156">Para obtener más información, vea [marcadores](bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="537d2-156">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="537d2-157">Quite la llamada a `WaitOne`y reemplácela con código para recopilar la entrada del usuario y reanudar el marcador <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="537d2-157">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="537d2-158">Quite la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="537d2-158">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="537d2-159">Reemplácela con el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="537d2-159">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="to-build-and-run-the-application"></a><a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="537d2-160">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="537d2-160">To build and run the application</span></span>

1. <span data-ttu-id="537d2-161">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en el **Explorador de soluciones** y seleccione **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="537d2-161">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="537d2-162">Presione CTRL+F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="537d2-162">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="537d2-163">Intente adivinar el número en los menos intentos posibles.</span><span class="sxs-lookup"><span data-stu-id="537d2-163">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="537d2-164">Para probar la aplicación con uno de los demás estilos de flujo de trabajo, reemplace `Workflow1` en el código que crea <xref:System.Activities.WorkflowApplication> por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del estilo de flujo de trabajo que desee.</span><span class="sxs-lookup"><span data-stu-id="537d2-164">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="537d2-165">Para obtener instrucciones sobre cómo agregar la persistencia a una aplicación de flujo de trabajo, consulte el siguiente tema: [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="537d2-165">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="537d2-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="537d2-166">Example</span></span>

 <span data-ttu-id="537d2-167">En el ejemplo siguiente se muestra la lista de código completa del método `Main` .</span><span class="sxs-lookup"><span data-stu-id="537d2-167">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
> <span data-ttu-id="537d2-168">Reemplace `Workflow1` en estos ejemplos por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del flujo de trabajo que completara en el paso [How to: Create a Workflow](how-to-create-a-workflow.md) anterior.</span><span class="sxs-lookup"><span data-stu-id="537d2-168">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="537d2-169">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="537d2-169">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="537d2-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="537d2-170">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="537d2-171">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="537d2-171">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="537d2-172">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="537d2-172">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="537d2-173">Procedimiento para crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-173">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="537d2-174">Procedimiento para crear y ejecutar un flujo de trabajo de larga duración</span><span class="sxs-lookup"><span data-stu-id="537d2-174">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="537d2-175">Esperar entrada en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-175">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="537d2-176">Hospedar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="537d2-176">Hosting Workflows</span></span>](hosting-workflows.md)
