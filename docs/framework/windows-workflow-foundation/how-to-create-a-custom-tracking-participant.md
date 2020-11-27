---
title: Procedimiento para crear un participante de seguimiento personalizado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b612c7e-2381-4a7c-b07a-77030415f2a3
ms.openlocfilehash: 5f00997b059d7ea6f6ac6fb6d7bd83e4515ac02a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275806"
---
# <a name="how-to-create-a-custom-tracking-participant"></a>Procedimiento para crear un participante de seguimiento personalizado

El seguimiento de flujo de trabajo proporciona visibilidad del estado de la ejecución del flujo de trabajo. El runtime de flujo de trabajo emite registros de seguimiento que describen los eventos de ciclo de vida de flujo de trabajo, los eventos de ciclo de vida de actividad, los errores y la reanudación de marcadores. Los participantes de seguimiento usan estos registros de seguimiento. Windows Workflow Foundation (WF) incluye un participante de seguimiento estándar que escribe los registros de seguimiento como eventos de seguimiento de eventos para Windows (ETW). Si eso no cumple sus requisitos, también puede escribir un participante de seguimiento personalizado. Este paso del tutorial describe cómo crear un participante y un perfil de seguimiento personalizados que capturen la salida de las actividades `WriteLine` para poder mostrarla al usuario.  
  
> [!NOTE]
> Cada uno de los temas del tutorial de introducción depende de los temas anteriores. Para completar este tema, primero debe finalizar los temas anteriores. Para descargar una versión completada o ver un tutorial en vídeo del tutorial, consulte [Windows Workflow Foundation (WF45)-Introducción tutorial](https://go.microsoft.com/fwlink/?LinkID=248976).  
  
## <a name="to-create-the-custom-tracking-participant"></a>Para crear el participante de seguimiento personalizado  
  
1. Haga clic con el botón secundario en **NumberGuessWorkflowHost** en **Explorador de soluciones** y elija **Agregar**, **clase**. Escriba `StatusTrackingParticipant` en el cuadro **nombre** y haga clic en **Agregar**.  
  
2. Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).  
  
    ```vb  
    Imports System.Activities.Tracking  
    Imports System.IO  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    using System.IO;  
    ```  
  
3. Modifique la clase `StatusTrackingParticipant` para que herede de `TrackingParticipant`.  
  
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
  
4. Agregue el siguiente remplazo de método `Track`. Hay varios tipos distintos de registros de seguimiento. Estamos interesados en el resultado de las actividades de `WriteLine` , contenidas en registros de seguimiento de actividad. Si `TrackingRecord` es un `ActivityTrackingRecord` para una actividad `WriteLine`, `Text` de `WriteLine` se anexa a un archivo con una nombre según `InstanceId` del flujo de trabajo. En este tutorial, el archivo se guarda en la carpeta actual de la aplicación de host.  
  
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
  
     Cuando no se especifica ningún perfil de seguimiento, se usa el perfil de seguimiento predeterminado. Cuando se usa el perfil de seguimiento predeterminado, los registros de seguimiento se emiten para todos `ActivityStates`. Dado que solo debemos capturar el texto una vez durante el ciclo de vida de la actividad `WriteLine` , solo extraemos el texto del estado `ActivityStates.Executing` . En [para crear el perfil de seguimiento y registrar el participante de seguimiento](#to-create-the-tracking-profile-and-register-the-tracking-participant), se crea un perfil de seguimiento que especifica que solo `WriteLine` `ActivityStates.Executing` se emiten los registros de seguimiento.  
  
## <a name="to-create-the-tracking-profile-and-register-the-tracking-participant"></a>Para crear el perfil de seguimiento y registrar el participante de seguimiento  
  
1. Haga clic con el botón secundario en **WorkflowHostForm** en **Explorador de soluciones** y elija **Ver código**.  
  
2. Agregue las siguientes instrucciones `using` (o `Imports`) al principio del archivo con las demás instrucciones `using` (o `Imports`).  
  
    ```vb  
    Imports System.Activities.Tracking  
    ```  
  
    ```csharp  
    using System.Activities.Tracking;  
    ```  
  
3. Agregue el código siguiente a `ConfigureWorkflowApplication` justo después del código que agrega `StringWriter` a las extensiones de flujo de trabajo y justo antes de los controladores de ciclo de vida de flujo de trabajo.  
  
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
  
     Este perfil de seguimiento especifica que solo los registros de estado de actividad para actividades `WriteLine` en el estado de `Executing` se emiten al participante de seguimiento personalizado.  
  
     Después de agregar el código, el inicio de `ConfigureWorkflowApplication` será como el ejemplo siguiente.  
  
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
  
## <a name="to-display-the-tracking-information"></a>Para mostrar la información de seguimiento  
  
1. Haga clic con el botón secundario en **WorkflowHostForm** en **Explorador de soluciones** y elija **Ver código**.  
  
2. En el controlador de `InstanceId_SelectedIndexChanged` , agregue el código siguiente inmediatamente después del código que borra la ventana de estado.  
  
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
  
     Cuando se selecciona un nuevo flujo de trabajo en la lista de flujos de trabajo, los registros de seguimiento para ese flujo de trabajo se cargan y se muestran en la ventana de estado. El siguiente ejemplo es el controlador `InstanceId_SelectedIndexChanged` completado.  
  
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
  
## <a name="to-build-and-run-the-application"></a>Para generar y ejecutar la aplicación  
  
1. Presione Ctrl+Mayús+B para compilar la aplicación.  
  
2. Presione Ctrl + F5 para iniciar la aplicación.  
  
3. Seleccione un intervalo para el juego de adivinación y el tipo de flujo de trabajo que se va a iniciar y haga clic en **nuevo juego**. Escriba una estimación en el cuadro de **estimación** y haga clic en **ir** para enviar su estimación. Observe que el estado del flujo de trabajo se muestra en la ventana de estado. Este resultado se captura de las actividades de `WriteLine`. Cambie a otro flujo de trabajo; para ello, seleccione uno en el cuadro combinado ID. de **instancia de flujo de trabajo** y observe que se ha quitado el estado del flujo de trabajo actual. Cambie de nuevo al flujo de trabajo anterior y observe que se restablece el estado, similar al siguiente ejemplo.  
  
    > [!NOTE]
    > Si cambia a un flujo de trabajo que se había iniciado antes de que se habilitara el seguimiento, no se mostrará ningún estado. Sin embargo, si hace intentos adicionales, el estado se guarda porque ahora se ha habilitado el seguimiento.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    > [!NOTE]
    > Esta información es útil para determinar el intervalo del número aleatorio, pero no contiene información sobre qué intentos se han hecho anteriormente. Esta información está en el paso siguiente, [Cómo: hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

    Anote el identificador de instancias de flujo de trabajo, y juegue hasta completar el juego.
  
4. Abra el explorador de Windows y navegue hasta la carpeta **NumberGuessWorkflowHost\bin\debug** (o **bin\release** según la configuración del proyecto). Observe que además de los archivos ejecutables del proyecto hay archivos con nombres de archivo guid. Identifique cuál corresponde al identificador de instancia del flujo de trabajo completado en el paso anterior y ábralo en el Bloc de notas. La información de seguimiento incluye información similar a la siguiente.  
  
    ```output
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    Your guess is too high.
    Please enter a number between 1 and 10
    ```

    Además de no contener los intentos del usuario, este dato de seguimiento no contiene información sobre el último intento del flujo de trabajo. Esto se debe a que la información de seguimiento solo consta del resultado de `WriteLine` del flujo de trabajo, y el mensaje final que se muestra se hace así desde el controlador de `Completed` una vez el flujo de trabajo se ha completado. En el siguiente paso del tutorial, [Cómo: hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md), `WriteLine` se modifican las actividades existentes para mostrar las conjeturas del usuario y `WriteLine` se agrega una actividad adicional que muestra los resultados finales. Una vez que estos cambios se han integrado, [Cómo: hospedar varias versiones de un flujo de trabajo en paralelo](how-to-host-multiple-versions-of-a-workflow-side-by-side.md) muestra cómo hospedar varias versiones de un flujo de trabajo al mismo tiempo.
