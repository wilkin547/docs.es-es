---
title: Filtrar para ejecutar un flujo de trabajo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f814ff82-fe2b-4614-aebb-b768c3e61179
ms.openlocfilehash: 06ac34f5ba5d95bd9f000a35036cf288d3c8f7f7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59319929"
---
# <a name="how-to-run-a-workflow"></a><span data-ttu-id="a8132-102">Filtrar para ejecutar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-102">How to: Run a Workflow</span></span>
<span data-ttu-id="a8132-103">En este tema es una continuación de Windows Workflow Foundation tutorial de introducción y se explica cómo crear un host de flujo de trabajo y ejecutar el flujo de trabajo definido en el anterior [Cómo: Crear un flujo de trabajo](how-to-create-a-workflow.md) tema.</span><span class="sxs-lookup"><span data-stu-id="a8132-103">This topic is a continuation of the Windows Workflow Foundation Getting Started tutorial and discusses how to create a workflow host and run the workflow defined in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="a8132-104">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="a8132-104">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="a8132-105">Para completar este tema, primero debe finalizar [Cómo: Crear una actividad](how-to-create-an-activity.md) y [Cómo: crear un flujo de trabajo](how-to-create-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a8132-105">To complete this topic you must first complete [How to: Create an Activity](how-to-create-an-activity.md) and [How to: Create a Workflow](how-to-create-a-workflow.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="a8132-106">Para descargar una versión completa del tutorial, consulte [Windows Workflow Foundation (WF45) - Getting Started Tutorial (Windows Workflow Foundation (WF45): tutorial introductorio)](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="a8132-106">To download a completed version of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
### <a name="to-create-the-workflow-host-project"></a><span data-ttu-id="a8132-107">Para crear el proyecto de host de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-107">To create the workflow host project</span></span>  
  
1. <span data-ttu-id="a8132-108">Abra la solución del anterior [Cómo: Crear una actividad](how-to-create-an-activity.md) tema mediante el uso de Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="a8132-108">Open the solution from the previous [How to: Create an Activity](how-to-create-an-activity.md) topic by using Visual Studio 2012.</span></span>  
  
2. <span data-ttu-id="a8132-109">Haga clic con el botón secundario en la solución **WF45GettingStartedTutorial** en el **Explorador de soluciones** y seleccione **Agregar**, **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a8132-109">Right-click the **WF45GettingStartedTutorial** solution in **Solution Explorer** and select **Add**, **New Project**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="a8132-110">Si la ventana **Explorador de soluciones** no se muestra, seleccione **Explorador de soluciones** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="a8132-110">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="a8132-111">En el nodo **Instalado** , seleccione **Visual C#**, **Flujo de trabajo** (o **Visual Basic**, **Flujo de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="a8132-111">In the **Installed** node, select **Visual C#**, **Workflow** (or **Visual Basic**, **Workflow**).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a8132-112">En función del lenguaje de programación que se configure como lenguaje principal en Visual Studio, el nodo **Visual C#** o **Visual Basic** puede estar bajo el nodo **Otros lenguajes** en el nodo **Instalado** .</span><span class="sxs-lookup"><span data-stu-id="a8132-112">Depending on which programming language is configured as the primary language in Visual Studio, the **Visual C#** or **Visual Basic** node may be under the **Other Languages** node in the **Installed** node.</span></span>

     <span data-ttu-id="a8132-113">Asegúrese de que se haya seleccionado **.NET Framework 4.5** en la lista desplegable correspondiente a la versión de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a8132-113">Ensure that **.NET Framework 4.5** is selected in the .NET Framework version drop-down list.</span></span> <span data-ttu-id="a8132-114">Seleccione **Aplicación de consola de flujos de trabajo** en la lista **Flujo de trabajo** .</span><span class="sxs-lookup"><span data-stu-id="a8132-114">Select **Workflow Console Application** from the **Workflow** list.</span></span> <span data-ttu-id="a8132-115">Escriba `NumberGuessWorkflowHost` en el cuadro **Nombre** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8132-115">Type `NumberGuessWorkflowHost` into the **Name** box and click **OK**.</span></span> <span data-ttu-id="a8132-116">Así se crea una aplicación de flujo de trabajo de inicio con soporte básico de hospedaje de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-116">This creates a starter workflow application with basic workflow hosting support.</span></span> <span data-ttu-id="a8132-117">Este código de hospedaje básico se modifica y se usa para ejecutar la aplicación de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-117">This basic hosting code is modified and used to run the workflow application.</span></span>

4. <span data-ttu-id="a8132-118">Haga clic con el botón secundario en el proyecto **NumberGuessWorkflowHost** recién agregado en el **Explorador de soluciones** y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a8132-118">Right-click the newly added **NumberGuessWorkflowHost** project in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="a8132-119">Seleccione **Solución** en la lista **Agregar referencia** , marque la casilla junto **NumberGuessWorkflowActivities**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8132-119">Select **Solution** from the **Add Reference** list, check the checkbox beside **NumberGuessWorkflowActivities**, and then click **OK**.</span></span>

5. <span data-ttu-id="a8132-120">Haga clic con el botón secundario en **Workflow1.xaml** en el **Explorador de soluciones** y elija **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="a8132-120">Right-click **Workflow1.xaml** in **Solution Explorer** and choose **Delete**.</span></span> <span data-ttu-id="a8132-121">Haga clic en **Aceptar** para confirmar.</span><span class="sxs-lookup"><span data-stu-id="a8132-121">Click **OK** to confirm.</span></span>

### <a name="to-modify-the-workflow-hosting-code"></a><span data-ttu-id="a8132-122">Para modificar el código de hospedaje de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-122">To modify the workflow hosting code</span></span>

1. <span data-ttu-id="a8132-123">Haga doble clic en **Program.cs** o en **Module1.vb** en el **Explorador de soluciones** para mostrar el código.</span><span class="sxs-lookup"><span data-stu-id="a8132-123">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to display the code.</span></span>

    > [!TIP]
    >  <span data-ttu-id="a8132-124">Si la ventana **Explorador de soluciones** no se muestra, seleccione **Explorador de soluciones** en el menú **Ver** .</span><span class="sxs-lookup"><span data-stu-id="a8132-124">If the **Solution Explorer** window is not displayed, select **Solution Explorer** from the **View** menu.</span></span>

     <span data-ttu-id="a8132-125">Dado que este proyecto se creó con la plantilla **Aplicación de consola de flujos de trabajo** , **Program.cs** o **Module1.vb** , contiene el siguiente código básico de hospedaje de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-125">Because this project was created by using the **Workflow Console Application** template, **Program.cs** or **Module1.vb** contains the following basic workflow hosting code.</span></span>

    ```vb
    ' Create and cache the workflow definition
    Activity workflow1 = new Workflow1()
    WorkflowInvoker.Invoke(workflow1)
    ```

    ```csharp
    // Create and cache the workflow definition
    Activity workflow1 = new Workflow1();
    WorkflowInvoker.Invoke(workflow1);
    ```

     <span data-ttu-id="a8132-126">Este código de hospedaje generado usa <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="a8132-126">This generated hosting code uses <xref:System.Activities.WorkflowInvoker>.</span></span> <xref:System.Activities.WorkflowInvoker> <span data-ttu-id="a8132-127">Proporciona una manera sencilla de invocar un flujo de trabajo como si fuera una llamada al método y se puede usar solo para los flujos de trabajo que no usan la persistencia.</span><span class="sxs-lookup"><span data-stu-id="a8132-127">provides a simple way for invoking a workflow as if it were a method call and can be used only for workflows that do not use persistence.</span></span> <xref:System.Activities.WorkflowApplication> <span data-ttu-id="a8132-128">Proporciona un modelo más enriquecido para ejecutar flujos de trabajo que incluye notificación de eventos de ciclo de vida, control de ejecución, reanudación de marcadores y persistencia.</span><span class="sxs-lookup"><span data-stu-id="a8132-128">provides a richer model for executing workflows that includes notification of life-cycle events, execution control, bookmark resumption, and persistence.</span></span> <span data-ttu-id="a8132-129">Este ejemplo usa marcadores y <xref:System.Activities.WorkflowApplication> se usa para hospedar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-129">This example uses bookmarks and <xref:System.Activities.WorkflowApplication> is used for hosting the workflow.</span></span> <span data-ttu-id="a8132-130">Agregue la siguiente instrucción `using` o **Imports** al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones **using** o **Imports** existentes.</span><span class="sxs-lookup"><span data-stu-id="a8132-130">Add the following `using` or **Imports** statement at the top of **Program.cs** or **Module1.vb** below the existing **using** or **Imports** statements.</span></span>

    ```vb
    Imports NumberGuessWorkflowActivities
    Imports System.Threading
    ```

    ```csharp
    using NumberGuessWorkflowActivities;
    using System.Threading;
    ```

     <span data-ttu-id="a8132-131">Reemplace las líneas de código que usan <xref:System.Activities.WorkflowInvoker> por el siguiente código básico de hospedaje <xref:System.Activities.WorkflowApplication> .</span><span class="sxs-lookup"><span data-stu-id="a8132-131">Replace the lines of code that use <xref:System.Activities.WorkflowInvoker> with the following basic <xref:System.Activities.WorkflowApplication> hosting code.</span></span> <span data-ttu-id="a8132-132">Este código de hospedaje de ejemplo muestra los pasos básicos para hospedar e invocar un flujo de trabajo, pero no contiene, sin embargo, la funcionalidad necesaria para ejecutar correctamente el flujo de trabajo en este tema.</span><span class="sxs-lookup"><span data-stu-id="a8132-132">This sample hosting code demonstrates the basic steps for hosting and invoking a workflow, but does not yet contain the functionality to successfully run the workflow from this topic.</span></span> <span data-ttu-id="a8132-133">En los pasos que figuran a continuación, el código básico se modifica y se agregan características adicionales hasta completar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8132-133">In the following steps, this basic code is modified and additional features are added until the application is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a8132-134">Reemplace `Workflow1` en estos ejemplos con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, o `StateMachineNumberGuessWorkflow`, en función de flujo de trabajo completara en el anterior [Cómo: Crear un flujo de trabajo](how-to-create-a-workflow.md) paso.</span><span class="sxs-lookup"><span data-stu-id="a8132-134">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="a8132-135">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-135">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#4](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#4)]
     [!code-vb[CFX_WF_GettingStarted#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#4)]

     <span data-ttu-id="a8132-136">Este código crea un objeto <xref:System.Activities.WorkflowApplication>, se suscribe a tres eventos de ciclo de vida de flujo de trabajo, inicia el flujo de trabajo con una llamada a <xref:System.Activities.WorkflowApplication.Run%2A>y espera a que el flujo de trabajo se complete.</span><span class="sxs-lookup"><span data-stu-id="a8132-136">This code creates a <xref:System.Activities.WorkflowApplication>, subscribes to three workflow life-cycle events, starts the workflow with a call to <xref:System.Activities.WorkflowApplication.Run%2A>, and then waits for the workflow to complete.</span></span> <span data-ttu-id="a8132-137">Cuando el flujo de trabajo finaliza, se establece <xref:System.Threading.AutoResetEvent> y se completa la aplicación host.</span><span class="sxs-lookup"><span data-stu-id="a8132-137">When the workflow completes, the <xref:System.Threading.AutoResetEvent> is set and the host application completes.</span></span>

### <a name="to-set-input-arguments-of-a-workflow"></a><span data-ttu-id="a8132-138">Para definir argumentos de entrada de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-138">To set input arguments of a workflow</span></span>

1. <span data-ttu-id="a8132-139">Agregue la siguiente instrucción al principio de **Program.cs** o **Module1.vb** debajo de las instrucciones `using` o `Imports` existentes.</span><span class="sxs-lookup"><span data-stu-id="a8132-139">Add the following statement at the top of **Program.cs** or **Module1.vb** below the existing `using` or `Imports` statements.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#5](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#5)]
     [!code-vb[CFX_WF_GettingStarted#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#5)]

2. <span data-ttu-id="a8132-140">Reemplace la línea de código que crea el nuevo <xref:System.Activities.WorkflowApplication> con el siguiente código que crea y pasa un diccionario de parámetros al flujo de trabajo cuando se crea.</span><span class="sxs-lookup"><span data-stu-id="a8132-140">Replace the line of code that creates the new <xref:System.Activities.WorkflowApplication> with the following code that creates and passes a dictionary of parameters to the workflow when it is created.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a8132-141">Reemplace `Workflow1` en estos ejemplos con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, o `StateMachineNumberGuessWorkflow`, en función de flujo de trabajo completara en el anterior [Cómo: Crear un flujo de trabajo](how-to-create-a-workflow.md) paso.</span><span class="sxs-lookup"><span data-stu-id="a8132-141">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="a8132-142">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-142">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="a8132-143">Este diccionario contiene un elemento con una clave de `MaxNumber`.</span><span class="sxs-lookup"><span data-stu-id="a8132-143">This dictionary contains one element with a key of `MaxNumber`.</span></span> <span data-ttu-id="a8132-144">Las claves del diccionario de entrada corresponden a argumentos de entrada en la actividad raíz del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-144">Keys in the input dictionary correspond to input arguments on the root activity of the workflow.</span></span> `MaxNumber` <span data-ttu-id="a8132-145">para determinar el límite superior para el número generado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="a8132-145">is used by the workflow to determine the upper bound for the randomly generated number.</span></span>

### <a name="to-retrieve-output-arguments-of-a-workflow"></a><span data-ttu-id="a8132-146">Para recuperar parámetros de salida de un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-146">To retrieve output arguments of a workflow</span></span>

1. <span data-ttu-id="a8132-147">Modifique el controlador <xref:System.Activities.WorkflowApplication.Completed%2A> para recuperar y mostrar el número de intentos que usó el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-147">Modify the <xref:System.Activities.WorkflowApplication.Completed%2A> handler to retrieve and display the number of turns used by the workflow.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#7](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#7)]
     [!code-vb[CFX_WF_GettingStarted#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#7)]

### <a name="to-resume-a-bookmark"></a><span data-ttu-id="a8132-148">Para reanudar un marcador</span><span class="sxs-lookup"><span data-stu-id="a8132-148">To resume a bookmark</span></span>

1. <span data-ttu-id="a8132-149">Agregue el siguiente código en la parte superior del método `Main` justo después de la declaración <xref:System.Threading.AutoResetEvent> existente.</span><span class="sxs-lookup"><span data-stu-id="a8132-149">Add the following code at the top of the `Main` method just after the existing <xref:System.Threading.AutoResetEvent> declaration.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#8](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#8)]
     [!code-vb[CFX_WF_GettingStarted#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#8)]

2. <span data-ttu-id="a8132-150">Agregue el siguiente controlador <xref:System.Activities.WorkflowApplication.Idle%2A> justo después de los tres controladores de ciclo de vida de flujo de trabajo existentes en `Main`.</span><span class="sxs-lookup"><span data-stu-id="a8132-150">Add the following <xref:System.Activities.WorkflowApplication.Idle%2A> handler just below the existing three workflow life-cycle handlers in `Main`.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#9](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#9)]
     [!code-vb[CFX_WF_GettingStarted#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#9)]

     <span data-ttu-id="a8132-151">Cada vez que el flujo de trabajo se vuelve inactiva, esperando la siguiente suposición, se llama a este controlador y el `idleAction` <xref:System.Threading.AutoResetEvent> está establecido.</span><span class="sxs-lookup"><span data-stu-id="a8132-151">Each time the workflow becomes idle waiting for the next guess, this handler is called and the `idleAction` <xref:System.Threading.AutoResetEvent> is set.</span></span> <span data-ttu-id="a8132-152">El código en el siguiente paso usa `idleEvent` y `syncEvent` para determinar si el flujo de trabajo está esperando la siguiente suposición o si se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a8132-152">The code in the following step uses `idleEvent` and `syncEvent` to determine whether the workflow is waiting for the next guess or is complete.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="a8132-153">En este ejemplo, la aplicación host usa eventos de restablecimiento automático en los controladores <xref:System.Activities.WorkflowApplication.Completed%2A> y <xref:System.Activities.WorkflowApplication.Idle%2A> para sincronizar la aplicación host con el progreso del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-153">In this example, the host application uses auto-reset events in the <xref:System.Activities.WorkflowApplication.Completed%2A> and <xref:System.Activities.WorkflowApplication.Idle%2A> handlers to synchronize the host application with the progress of the workflow.</span></span> <span data-ttu-id="a8132-154">No es necesario bloquear y esperar a que el flujo de trabajo se vuelva inactivo para reanudar un marcador, aunque en este ejemplo los eventos de sincronización resultan necesarios para que el host sepa si se ha completado el flujo de trabajo o si está esperando más entradas de usuario mediante <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="a8132-154">It is not necessary to block and wait for the workflow to become idle before resuming a bookmark, but in this example the synchronization events are required so the host knows whether the workflow is complete or whether it is waiting on more user input by using the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="a8132-155">Para obtener más información, consulte [marcadores](bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="a8132-155">For more information, see [Bookmarks](bookmarks.md).</span></span>

3. <span data-ttu-id="a8132-156">Quite la llamada a `WaitOne`y reemplácela con código para recopilar la entrada del usuario y reanudar el marcador <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="a8132-156">Remove the call to `WaitOne`, and replace it with code to gather input from the user and resume the <xref:System.Activities.Bookmark>.</span></span>

     <span data-ttu-id="a8132-157">Quite la siguiente línea de código.</span><span class="sxs-lookup"><span data-stu-id="a8132-157">Remove the following line of code.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#10](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/extrasnippets.cs#10)]
     [!code-vb[CFX_WF_GettingStarted#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/extrasnippets.vb#10)]

     <span data-ttu-id="a8132-158">Reemplácela con el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a8132-158">Replace it with the following example.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#11](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#11)]
     [!code-vb[CFX_WF_GettingStarted#11](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#11)]

## <a name="BKMK_ToRunTheApplication"></a> <span data-ttu-id="a8132-159">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="a8132-159">To build and run the application</span></span>

1. <span data-ttu-id="a8132-160">Haga clic con el botón secundario en **NumberGuessWorkflowHost** en el **Explorador de soluciones** y seleccione **Establecer como proyecto de inicio**.</span><span class="sxs-lookup"><span data-stu-id="a8132-160">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and select **Set as StartUp Project**.</span></span>

2. <span data-ttu-id="a8132-161">Presione CTRL+F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a8132-161">Press CTRL+F5 to build and run the application.</span></span> <span data-ttu-id="a8132-162">Intente adivinar el número en los menos intentos posibles.</span><span class="sxs-lookup"><span data-stu-id="a8132-162">Try to guess the number in as few turns as possible.</span></span>

     <span data-ttu-id="a8132-163">Para probar la aplicación con uno de los demás estilos de flujo de trabajo, reemplace `Workflow1` en el código que crea <xref:System.Activities.WorkflowApplication> por `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`o `StateMachineNumberGuessWorkflow`, en función del estilo de flujo de trabajo que desee.</span><span class="sxs-lookup"><span data-stu-id="a8132-163">To try the application with one of the other styles of workflow, replace `Workflow1` in the code that creates the <xref:System.Activities.WorkflowApplication> with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow style you desire.</span></span>

     [!code-csharp[CFX_WF_GettingStarted#6](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#6)]
     [!code-vb[CFX_WF_GettingStarted#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#6)]

     <span data-ttu-id="a8132-164">Para obtener instrucciones sobre cómo agregar la persistencia a una aplicación de flujo de trabajo, vea el tema siguiente, [Cómo: Crear y ejecutar una larga ejecución de flujo de trabajo](how-to-create-and-run-a-long-running-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="a8132-164">For instructions about how to add persistence to a workflow application, see the next topic, [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md).</span></span>

## <a name="example"></a><span data-ttu-id="a8132-165">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8132-165">Example</span></span>
 <span data-ttu-id="a8132-166">En el ejemplo siguiente se muestra la lista de código completa del método `Main` .</span><span class="sxs-lookup"><span data-stu-id="a8132-166">The following example is the complete code listing for the `Main` method.</span></span>

> [!NOTE]
>  <span data-ttu-id="a8132-167">Reemplace `Workflow1` en estos ejemplos con `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, o `StateMachineNumberGuessWorkflow`, en función de flujo de trabajo completara en el anterior [Cómo: Crear un flujo de trabajo](how-to-create-a-workflow.md) paso.</span><span class="sxs-lookup"><span data-stu-id="a8132-167">Please replace `Workflow1` in these examples with `FlowchartNumberGuessWorkflow`, `SequentialNumberGuessWorkflow`, or `StateMachineNumberGuessWorkflow`, depending on which workflow you completed in the previous [How to: Create a Workflow](how-to-create-a-workflow.md) step.</span></span> <span data-ttu-id="a8132-168">Si no reemplaza `Workflow1` , se producirán errores de compilación cuando intente compilar o ejecutar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8132-168">If you do not replace `Workflow1` then you will get build errors when you try and build or run the workflow.</span></span>

 [!code-csharp[CFX_WF_GettingStarted#12](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_wf_gettingstarted/cs/program.cs#12)]
 [!code-vb[CFX_WF_GettingStarted#12](~/samples/snippets/visualbasic/VS_Snippets_CFX/cfx_wf_gettingstarted/vb/module1.vb#12)]

## <a name="see-also"></a><span data-ttu-id="a8132-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8132-169">See also</span></span>

- <xref:System.Activities.WorkflowApplication>
- <xref:System.Activities.Bookmark>
- [<span data-ttu-id="a8132-170">Programación de Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="a8132-170">Windows Workflow Foundation Programming</span></span>](programming.md)
- [<span data-ttu-id="a8132-171">Tutorial de introducción</span><span class="sxs-lookup"><span data-stu-id="a8132-171">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="a8132-172">Filtrar para crear un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-172">How to: Create a Workflow</span></span>](how-to-create-a-workflow.md)
- [<span data-ttu-id="a8132-173">Filtrar para crear y ejecutar un flujo de trabajo de larga duración</span><span class="sxs-lookup"><span data-stu-id="a8132-173">How to: Create and Run a Long Running Workflow</span></span>](how-to-create-and-run-a-long-running-workflow.md)
- [<span data-ttu-id="a8132-174">Esperar entrada en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-174">Waiting for Input in a Workflow</span></span>](waiting-for-input-in-a-workflow.md)
- [<span data-ttu-id="a8132-175">Hospedar flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8132-175">Hosting Workflows</span></span>](hosting-workflows.md)