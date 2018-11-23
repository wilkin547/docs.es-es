---
title: Cómo crear un participante de seguimiento personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: a9a83f64b7ea0de275631d7d3b8d2755671223ce
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864487"
---
# <a name="how-to-create-a-custom-tracking-participant"></a><span data-ttu-id="4c980-102">Cómo crear un participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="4c980-102">How to: Create a Custom Tracking Participant</span></span>
<span data-ttu-id="4c980-103">El seguimiento de flujo de trabajo proporciona visibilidad del estado de la ejecución del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c980-103">Workflow tracking provides visibility into the status of workflow execution.</span></span> <span data-ttu-id="4c980-104">El runtime de flujo de trabajo emite registros de seguimiento que describen los eventos de ciclo de vida de flujo de trabajo, los eventos de ciclo de vida de actividad, los errores y la reanudación de marcadores.</span><span class="sxs-lookup"><span data-stu-id="4c980-104">The workflow runtime emits tracking records that describe workflow lifecycle events, activity lifecycle events, bookmark resumptions, and faults.</span></span> <span data-ttu-id="4c980-105">Los participantes de seguimiento usan estos registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4c980-105">These tracking records are consumed by tracking participants.</span></span> <span data-ttu-id="4c980-106">Windows Workflow Foundation (WF) incluye a un participante de seguimiento estándar que escribe registros de seguimiento como eventos de seguimiento de eventos para Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="4c980-106">Windows Workflow Foundation (WF) includes a standard tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span> <span data-ttu-id="4c980-107">Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="4c980-107">If that does not meet your requirements, you can also write a custom tracking participant.</span></span> <span data-ttu-id="4c980-108">Este paso del tutorial describe cómo crear un participante y un perfil de seguimiento personalizados que capturen la salida de las actividades `WriteLine` para poder mostrarla al usuario.</span><span class="sxs-lookup"><span data-stu-id="4c980-108">This tutorial step describes how to create a custom tracking participant and tracking profile that capture the output of `WriteLine` activities so that they can be displayed to the user.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c980-109">Cada uno de los temas del tutorial de introducción depende de los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4c980-109">Each topic in the Getting Started tutorial depends on the previous topics.</span></span> <span data-ttu-id="4c980-110">Para completar este tema, primero debe finalizar los temas anteriores.</span><span class="sxs-lookup"><span data-stu-id="4c980-110">To complete this topic, you must first complete the previous topics.</span></span> <span data-ttu-id="4c980-111">Para descargar una versión completada o ver un tutorial en vídeo del tutorial, vea [Windows Workflow Foundation (WF45): Tutorial de introducción](https://go.microsoft.com/fwlink/?LinkID=248976).</span><span class="sxs-lookup"><span data-stu-id="4c980-111">To download a completed version or view a video walkthrough of the tutorial, see [Windows Workflow Foundation (WF45) - Getting Started Tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).</span></span>  
  
## <a name="in-this-topic"></a><span data-ttu-id="4c980-112">En este tema</span><span class="sxs-lookup"><span data-stu-id="4c980-112">In this topic</span></span>  
  
-   [<span data-ttu-id="4c980-113">Para crear al participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="4c980-113">To create the custom tracking participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_CustomTrackingParticipant)  
  
-   [<span data-ttu-id="4c980-114">Para crear el perfil de seguimiento y registrar al participante de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4c980-114">To create the tracking profile and register the tracking participant</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile)  
  
-   [<span data-ttu-id="4c980-115">Para mostrar la información de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4c980-115">To display the tracking information</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_DisplayTracking)  
  
-   [<span data-ttu-id="4c980-116">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4c980-116">To build and run the application</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_BuildAndRun)  
  
###  <a name="BKMK_CustomTrackingParticipant"></a> <span data-ttu-id="4c980-117">Para crear al participante de seguimiento personalizado</span><span class="sxs-lookup"><span data-stu-id="4c980-117">To create the custom tracking participant</span></span>  
  
1.  <span data-ttu-id="4c980-118">Haga clic en **NumberGuessWorkflowHost** en **el Explorador de soluciones** y elija **agregar**, **clase**.</span><span class="sxs-lookup"><span data-stu-id="4c980-118">Right-click **NumberGuessWorkflowHost** in **Solution Explorer** and choose **Add**, **Class**.</span></span> <span data-ttu-id="4c980-119">Tipo `StatusTrackingParticipant` en el **nombre** cuadro y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="4c980-119">Type `StatusTrackingParticipant` into the **Name** box, and click **Add**.</span></span>  
  
2.  <span data-ttu-id="4c980-120">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="4c980-120">Add the following `using` (or `Imports`) statements at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3.  <span data-ttu-id="4c980-121">Modifique la clase `StatusTrackingParticipant` para que herede de `TrackingParticipant`.</span><span class="sxs-lookup"><span data-stu-id="4c980-121">Modify the `StatusTrackingParticipant` class so that it inherits from `TrackingParticipant`.</span></span>  
  
    ```vb  
    Public Class StatusTrackingParticipant  
        Inherits TrackingParticipant  
  
    End Class  
    ```  
  
    ```csharp  
    class StatusTrackingParticipant : TrackingParticipant  
    {  
    }  
    ```  
  
4.  <span data-ttu-id="4c980-122">Agregue el siguiente remplazo de método `Track`.</span><span class="sxs-lookup"><span data-stu-id="4c980-122">Add the following `Track` method override.</span></span> <span data-ttu-id="4c980-123">Hay varios tipos distintos de registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4c980-123">There are several different types of tracking records.</span></span> <span data-ttu-id="4c980-124">Estamos interesados en el resultado de las actividades de `WriteLine` , contenidas en registros de seguimiento de actividad.</span><span class="sxs-lookup"><span data-stu-id="4c980-124">We are interested in the output of `WriteLine` activities, which are contained in activity tracking records.</span></span> <span data-ttu-id="4c980-125">Si `TrackingRecord` es un `ActivityTrackingRecord` para una actividad `WriteLine`, `Text` de `WriteLine` se anexa a un archivo con una nombre según `InstanceId` del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c980-125">If the `TrackingRecord` is an `ActivityTrackingRecord` for a `WriteLine` activity, the `Text` of the `WriteLine` is appended to a file named after the `InstanceId` of the workflow.</span></span> <span data-ttu-id="4c980-126">En este tutorial, el archivo se guarda en la carpeta actual de la aplicación de host.</span><span class="sxs-lookup"><span data-stu-id="4c980-126">In this tutorial, the file is saved to the current folder of the host application.</span></span>  
  
    ```vb  
    Protected Overrides Sub Track(record As TrackingRecord, timeout As TimeSpan)  
        Dim asr As ActivityStateRecord = TryCast(record, ActivityStateRecord)  
  
        If Not asr Is Nothing Then  
            If asr.State = ActivityStates.Executing And _  
            asr.Activity.TypeName = "System.Activities.Statements.WriteLine" Then  
  
                'Append the WriteLine output to the tracking  
                'file for this instance.  
                Using writer As StreamWriter = File.AppendText(record.InstanceId.ToString())  
                    writer.WriteLine(asr.Arguments("Text"))  
                    writer.Close()  
                End Using  
            End If  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    protected override void Track(TrackingRecord record, TimeSpan timeout)  
    {  
        ActivityStateRecord asr = record as ActivityStateRecord;  
  
        if (asr != null)  
        {  
            if (asr.State == ActivityStates.Executing &&  
                asr.Activity.TypeName == "System.Activities.Statements.WriteLine")  
            {  
                // Append the WriteLine output to the tracking  
                // file for this instance  
                using (StreamWriter writer = File.AppendText(record.InstanceId.ToString()))  
                {  
                    writer.WriteLine(asr.Arguments["Text"]);  
                    writer.Close();  
                }  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="4c980-127">Cuando no se especifica ningún perfil de seguimiento, se usa el perfil de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4c980-127">When no tracking profile is specified, the default tracking profile is used.</span></span> <span data-ttu-id="4c980-128">Cuando se usa el perfil de seguimiento predeterminado, los registros de seguimiento se emiten para todos `ActivityStates`.</span><span class="sxs-lookup"><span data-stu-id="4c980-128">When the default tracking profile is used, tracking records are emitted for all `ActivityStates`.</span></span> <span data-ttu-id="4c980-129">Dado que solo debemos capturar el texto una vez durante el ciclo de vida de la actividad `WriteLine` , solo extraemos el texto del estado `ActivityStates.Executing` .</span><span class="sxs-lookup"><span data-stu-id="4c980-129">Because we only need to capture the text one time during the lifecycle of the `WriteLine` activity, we only extract the text from the `ActivityStates.Executing` state.</span></span> <span data-ttu-id="4c980-130">En [para crear el perfil de seguimiento y registrar el participante de seguimiento](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile), se crea un perfil de seguimiento que especifica que solo `WriteLine` `ActivityStates.Executing` se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4c980-130">In [To create the tracking profile and register the tracking participant](../../../docs/framework/windows-workflow-foundation/how-to-create-a-custom-tracking-participant.md#BKMK_TrackingProfile), a tracking profile is created that specifies that only `WriteLine` `ActivityStates.Executing` tracking records are emitted.</span></span>  
  
###  <a name="BKMK_TrackingProfile"></a> <span data-ttu-id="4c980-131">Para crear el perfil de seguimiento y registrar al participante de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4c980-131">To create the tracking profile and register the tracking participant</span></span>  
  
1.  <span data-ttu-id="4c980-132">Haga clic en **WorkflowHostForm** en **el Explorador de soluciones** y elija **ver código**.</span><span class="sxs-lookup"><span data-stu-id="4c980-132">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="4c980-133">Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).</span><span class="sxs-lookup"><span data-stu-id="4c980-133">Add the following `using` (or `Imports`) statement at the top of the file with the other `using` (or `Imports`) statements.</span></span>  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3.  <span data-ttu-id="4c980-134">Agregue el código siguiente a `ConfigureWorkflowApplication` justo después del código que agrega `StringWriter` a las extensiones de flujo de trabajo y justo antes de los controladores de ciclo de vida de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c980-134">Add the following code to `ConfigureWorkflowApplication` just after the code that adds the `StringWriter` to the workflow extensions and before the workflow lifecycle handlers.</span></span>  
  
    ```vb  
    'Add the custom tracking participant with a tracking profile  
    'that only emits tracking records for WriteLine activities.  
    Dim query As New ActivityStateQuery()  
    query.ActivityName = "WriteLine"  
    query.States.Add(ActivityStates.Executing)  
    query.Arguments.Add("Text")  
  
    Dim profile As New TrackingProfile()  
    profile.Queries.Add(query)  
  
    Dim stp As New StatusTrackingParticipant()  
    stp.TrackingProfile = profile  
  
    wfApp.Extensions.Add(stp)  
    ```  
  
    ```csharp  
    // Add the custom tracking participant with a tracking profile  
    // that only emits tracking records for WriteLine activities.  
    StatusTrackingParticipant stp = new StatusTrackingParticipant  
    {  
        TrackingProfile = new TrackingProfile  
        {  
            Queries =   
            {  
                new ActivityStateQuery  
                {  
                    ActivityName = "WriteLine",  
                    States = { ActivityStates.Executing },  
                    Arguments = { "Text" }  
                }  
            }  
        }  
    };  
  
    wfApp.Extensions.Add(stp);  
    ```  
  
     <span data-ttu-id="4c980-135">Este perfil de seguimiento especifica que solo los registros de estado de actividad para actividades `WriteLine` en el estado de `Executing` se emiten al participante de seguimiento personalizado.</span><span class="sxs-lookup"><span data-stu-id="4c980-135">This tracking profile specifies that only activity state records for `WriteLine` activities in the `Executing` state are emitted to the custom tracking participant.</span></span>  
  
     <span data-ttu-id="4c980-136">Después de agregar el código, el inicio de `ConfigureWorkflowApplication` será como el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c980-136">After adding the code, the start of `ConfigureWorkflowApplication` will look like the following example.</span></span>  
  
    ```vb  
    Private Sub ConfigureWorkflowApplication(wfApp As WorkflowApplication)  
        'Configure the persistence store.  
        wfApp.InstanceStore = store  
  
        'Add a StringWriter to the extensions. This captures the output  
        'from the WriteLine activities so we can display it in the form.  
        Dim sw As New StringWriter()  
        wfApp.Extensions.Add(sw)  
  
        'Add the custom tracking participant with a tracking profile  
        'that only emits tracking records for WriteLine activities.  
        Dim query As New ActivityStateQuery()  
        query.ActivityName = "WriteLine"  
        query.States.Add(ActivityStates.Executing)  
        query.Arguments.Add("Text")  
  
        Dim profile As New TrackingProfile()  
        profile.Queries.Add(query)  
  
        Dim stp As New StatusTrackingParticipant()  
        stp.TrackingProfile = profile  
  
        wfApp.Extensions.Add(stp)  
  
        'Workflow lifecycle handlers...  
    ```  
  
    ```csharp  
    private void ConfigureWorkflowApplication(WorkflowApplication wfApp)  
    {  
        // Configure the persistence store.  
        wfApp.InstanceStore = store;  
  
        // Add a StringWriter to the extensions. This captures the output  
        // from the WriteLine activities so we can display it in the form.  
        StringWriter sw = new StringWriter();  
        wfApp.Extensions.Add(sw);  
  
        // Add the custom tracking participant with a tracking profile  
        // that only emits tracking records for WriteLine activities.  
        StatusTrackingParticipant stp = new StatusTrackingParticipant  
        {  
            TrackingProfile = new TrackingProfile  
            {  
                Queries =   
                {  
                    new ActivityStateQuery  
                    {  
                        ActivityName = "WriteLine",  
                        States = { ActivityStates.Executing },  
                        Arguments = { "Text" }  
                    }  
                }  
            }  
        };  
  
        wfApp.Extensions.Add(stp);  
  
        // Workflow lifecycle handlers...  
    ```  
  
###  <a name="BKMK_DisplayTracking"></a> <span data-ttu-id="4c980-137">Para mostrar la información de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4c980-137">To display the tracking information</span></span>  
  
1.  <span data-ttu-id="4c980-138">Haga clic en **WorkflowHostForm** en **el Explorador de soluciones** y elija **ver código**.</span><span class="sxs-lookup"><span data-stu-id="4c980-138">Right-click **WorkflowHostForm** in **Solution Explorer** and choose **View Code**.</span></span>  
  
2.  <span data-ttu-id="4c980-139">En el controlador de `InstanceId_SelectedIndexChanged` , agregue el código siguiente inmediatamente después del código que borra la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4c980-139">In the `InstanceId_SelectedIndexChanged` handler, add the following code immediately after the code that clears the status window.</span></span>  
  
    ```vb  
    'If there is tracking data for this workflow, display it  
    'in the status window.  
    If File.Exists(WorkflowInstanceId.ToString()) Then  
        Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
        UpdateStatus(status)  
    End If  
    ```  
  
    ```csharp  
    // If there is tracking data for this workflow, display it  
    // in the status window.  
    if (File.Exists(WorkflowInstanceId.ToString()))  
    {  
        string status = File.ReadAllText(WorkflowInstanceId.ToString());  
        UpdateStatus(status);  
    }  
    ```  
  
     <span data-ttu-id="4c980-140">Cuando se selecciona un nuevo flujo de trabajo en la lista de flujos de trabajo, los registros de seguimiento para ese flujo de trabajo se cargan y se muestran en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4c980-140">When a new workflow is selected in the workflow list, the tracking records for that workflow are loaded and displayed in the status window.</span></span> <span data-ttu-id="4c980-141">El siguiente ejemplo es el controlador `InstanceId_SelectedIndexChanged` completado.</span><span class="sxs-lookup"><span data-stu-id="4c980-141">The following example is the completed `InstanceId_SelectedIndexChanged` handler.</span></span>  
  
    ```vb  
    Private Sub InstanceId_SelectedIndexChanged(sender As Object, e As EventArgs) Handles InstanceId.SelectedIndexChanged  
        If InstanceId.SelectedIndex = -1 Then  
            Return  
        End If  
  
        'Clear the status window.  
        WorkflowStatus.Clear()  
  
        'If there is tracking data for this workflow, display it  
        'in the status window.  
        If File.Exists(WorkflowInstanceId.ToString()) Then  
            Dim status As String = File.ReadAllText(WorkflowInstanceId.ToString())  
            UpdateStatus(status)  
        End If  
  
        'Get the workflow version and display it.  
        'If the workflow is just starting then this info will not  
        'be available in the persistence store so do not try and retrieve it.  
        If Not WorkflowStarting Then  
            Dim instance As WorkflowApplicationInstance = _  
                WorkflowApplication.GetInstance(WorkflowInstanceId, store)  
  
            WorkflowVersion.Text = _  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity)  
  
            'Unload the instance.  
            instance.Abandon()  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void InstanceId_SelectedIndexChanged(object sender, EventArgs e)  
    {  
        if (InstanceId.SelectedIndex == -1)  
        {  
            return;  
        }  
  
        // Clear the status window.  
        WorkflowStatus.Clear();  
  
        // If there is tracking data for this workflow, display it  
        // in the status window.  
        if (File.Exists(WorkflowInstanceId.ToString()))  
        {  
            string status = File.ReadAllText(WorkflowInstanceId.ToString());  
            UpdateStatus(status);  
        }  
  
        // Get the workflow version and display it.  
        // If the workflow is just starting then this info will not  
        // be available in the persistence store so do not try and retrieve it.  
        if (!WorkflowStarting)  
        {  
            WorkflowApplicationInstance instance =  
                WorkflowApplication.GetInstance(this.WorkflowInstanceId, store);  
  
            WorkflowVersion.Text =  
                WorkflowVersionMap.GetIdentityDescription(instance.DefinitionIdentity);  
  
            // Unload the instance.  
            instance.Abandon();  
        }  
    }  
    ```  
  
###  <a name="BKMK_BuildAndRun"></a> <span data-ttu-id="4c980-142">Para compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4c980-142">To build and run the application</span></span>  
  
1.  <span data-ttu-id="4c980-143">Presione Ctrl+Mayús+B para compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c980-143">Press Ctrl+Shift+B to build the application.</span></span>  
  
2.  <span data-ttu-id="4c980-144">Presione Ctrl + F5 para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c980-144">Press Ctrl+F5 to start the application.</span></span>  
  
3.  <span data-ttu-id="4c980-145">Seleccionar un intervalo para el juego de Adivinanzas de números y el tipo de flujo de trabajo para iniciar y haga clic en **New Game**.</span><span class="sxs-lookup"><span data-stu-id="4c980-145">Select a range for the guessing game and the type of workflow to start, and click **New Game**.</span></span> <span data-ttu-id="4c980-146">Escriba un intento en el **estimación** y haga clic en **vaya** para enviarlo.</span><span class="sxs-lookup"><span data-stu-id="4c980-146">Enter a guess in the **Guess** box and click **Go** to submit your guess.</span></span> <span data-ttu-id="4c980-147">Observe que el estado del flujo de trabajo se muestra en la ventana de estado.</span><span class="sxs-lookup"><span data-stu-id="4c980-147">Note that the status of the workflow is displayed in the status window.</span></span> <span data-ttu-id="4c980-148">Este resultado se captura de las actividades de `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="4c980-148">This output is captured from the `WriteLine` activities.</span></span> <span data-ttu-id="4c980-149">Cambiar a un flujo de trabajo diferente seleccionando uno de los **Id. de instancia de flujo de trabajo** cuadro combinado y tenga en cuenta que se ha quitado el estado del flujo de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="4c980-149">Switch to a different workflow by selecting one from the **Workflow Instance Id** combo box and note that the status of the current workflow is removed.</span></span> <span data-ttu-id="4c980-150">Cambie de nuevo al flujo de trabajo anterior y observe que se restablece el estado, similar al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4c980-150">Switch back to the previous workflow and note that the status is restored, similar to the following example.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c980-151">Si cambia a un flujo de trabajo que se había iniciado antes de que se habilitara el seguimiento, no se mostrará ningún estado.</span><span class="sxs-lookup"><span data-stu-id="4c980-151">If you switch to a workflow that was started before tracking was enabled no status is displayed.</span></span> <span data-ttu-id="4c980-152">Sin embargo, si hace intentos adicionales, el estado se guarda porque ahora se ha habilitado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4c980-152">However if you make additional guesses, their status is saved because tracking is now enabled.</span></span>  
  
 <span data-ttu-id="4c980-153">**Escriba un número entre 1 y 10**</span><span class="sxs-lookup"><span data-stu-id="4c980-153">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="4c980-154">**Su intento es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4c980-154">**Your guess is too high.** </span></span>  
<span data-ttu-id="4c980-155">**Escriba un número entre 1 y 10**</span><span class="sxs-lookup"><span data-stu-id="4c980-155">**Please enter a number between 1 and 10**</span></span>    
    > [!NOTE]
    >  <span data-ttu-id="4c980-156">Esta información es útil para determinar el intervalo del número aleatorio, pero no contiene información sobre qué intentos se han hecho anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4c980-156">This information is useful for determining the range of the random number, but it does not contain any information about what guesses have been previously made.</span></span> <span data-ttu-id="4c980-157">Esta información está en el paso siguiente, [How to: Host varias versiones de un flujo de trabajo Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span><span class="sxs-lookup"><span data-stu-id="4c980-157">This information is in the next step, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md).</span></span>  
  
     <span data-ttu-id="4c980-158">Anote el identificador de instancias de flujo de trabajo, y juegue hasta completar el juego.</span><span class="sxs-lookup"><span data-stu-id="4c980-158">Make a note of the workflow instance id, and play the game through to its completion.</span></span>  
  
4.  <span data-ttu-id="4c980-159">Abra el Explorador de Windows y navegue hasta la **NumberGuessWorkflowHost\bin\debug** carpeta (o **bin\release** según la configuración del proyecto).</span><span class="sxs-lookup"><span data-stu-id="4c980-159">Open Windows Explorer and navigate to the **NumberGuessWorkflowHost\bin\debug** folder (or **bin\release** depending on your project settings).</span></span> <span data-ttu-id="4c980-160">Observe que además de los archivos ejecutables del proyecto hay archivos con nombres de archivo guid.</span><span class="sxs-lookup"><span data-stu-id="4c980-160">Note that in addition to the project executable files there are files with guid filenames.</span></span> <span data-ttu-id="4c980-161">Identifique cuál corresponde al identificador de instancia del flujo de trabajo completado en el paso anterior y ábralo en el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="4c980-161">Identify the one that corresponds to the workflow instance id from the completed workflow in the previous step and open it in Notepad.</span></span> <span data-ttu-id="4c980-162">La información de seguimiento incluye información similar a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c980-162">The tracking information contains information similar to the following.</span></span>  
  
 <span data-ttu-id="4c980-163">**Escriba un número entre 1 y 10**</span><span class="sxs-lookup"><span data-stu-id="4c980-163">**Please enter a number between 1 and 10**</span></span>  
<span data-ttu-id="4c980-164">**Su intento es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4c980-164">**Your guess is too high.** </span></span>  
<span data-ttu-id="4c980-165">**Escriba un número entre 1 y 10** </span><span class="sxs-lookup"><span data-stu-id="4c980-165">**Please enter a number between 1 and 10** </span></span>  
<span data-ttu-id="4c980-166">**Su intento es demasiado alto.** </span><span class="sxs-lookup"><span data-stu-id="4c980-166">**Your guess is too high.** </span></span>  
<span data-ttu-id="4c980-167">**Escriba un número entre 1 y 10** además de la ausencia de los intentos del usuario, estos datos de seguimiento no contienen información sobre el último intento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4c980-167">**Please enter a number between 1 and 10**      In addition to the absence of the user's guesses, this tracking data does not contain information about the final guess of the workflow.</span></span> <span data-ttu-id="4c980-168">Esto se debe a que la información de seguimiento solo consta del resultado de `WriteLine` del flujo de trabajo, y el mensaje final que se muestra se hace así desde el controlador de `Completed` una vez el flujo de trabajo se ha completado.</span><span class="sxs-lookup"><span data-stu-id="4c980-168">That is because the tracking information consists only of the `WriteLine` output from the workflow, and the final message that is displayed is done so from the `Completed` handler after the workflow completes.</span></span> <span data-ttu-id="4c980-169">En el siguiente paso del tutorial, [Cómo: Host varias versiones de un flujo de trabajo Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), existente `WriteLine` se modifican las actividades para mostrar los intentos del usuario y más `WriteLine` que agregar actividad Muestra el resultado final.</span><span class="sxs-lookup"><span data-stu-id="4c980-169">In next step of the tutorial, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md), the existing `WriteLine` activities are modified to display the user's guesses, and an additional `WriteLine` activity is added that displays the final results.</span></span> <span data-ttu-id="4c980-170">Después de que estos cambios se han integrado, [How to: Host varias versiones de un flujo de trabajo Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) muestra cómo hospedar varias versiones de un flujo de trabajo al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4c980-170">After these changes are integrated, [How to: Host Multiple Versions of a Workflow Side-by-Side](../../../docs/framework/windows-workflow-foundation/how-to-host-multiple-versions-of-a-workflow-side-by-side.md) demonstrates how to host multiple versions of a workflow at the same time.</span></span>
