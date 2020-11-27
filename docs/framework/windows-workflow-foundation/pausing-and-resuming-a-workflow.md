---
title: Pausar y reanudar un flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 11f38339-79c7-4295-b610-24a7223bbf6d
ms.openlocfilehash: e8d1806c6d2c8e72b4e3a8b18bff669fcd0e0538
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268545"
---
# <a name="pausing-and-resuming-a-workflow"></a><span data-ttu-id="e8c20-102">Pausar y reanudar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e8c20-102">Pausing and Resuming a Workflow</span></span>

<span data-ttu-id="e8c20-103">Los flujos de trabajo pausarán y se reanudarán en respuesta a los marcadores y actividades de bloqueo, como <xref:System.Activities.Statements.Delay>, pero un flujo de trabajo puede ser explicitamente pausado, descargado y reanudado utilizando la persistencia.</span><span class="sxs-lookup"><span data-stu-id="e8c20-103">Workflows will pause and resume in response to bookmarks and blocking activities such as <xref:System.Activities.Statements.Delay>, but a workflow can also be explicitly paused, unloaded, and resumed by using persistence.</span></span>  
  
## <a name="pausing-a-workflow"></a><span data-ttu-id="e8c20-104">Pausar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e8c20-104">Pausing a Workflow</span></span>  

 <span data-ttu-id="e8c20-105">Para pausar un flujo de trabajo, utilice <xref:System.Activities.WorkflowApplication.Unload%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8c20-105">To pause a workflow, use <xref:System.Activities.WorkflowApplication.Unload%2A>.</span></span>  <span data-ttu-id="e8c20-106">Este método solicita que el flujo de trabajo se guarde y descargue, y producirá una excepción <xref:System.TimeoutException> si el flujo de trabajo no se descarga en 30 segundos.</span><span class="sxs-lookup"><span data-stu-id="e8c20-106">This method requests that the workflow persist and unload, and will throw a <xref:System.TimeoutException> if the workflow does not unload in 30 seconds.</span></span>  
  
```csharp  
try  
{  
    // attempt to unload will fail if the workflow is idle within a NoPersistZone  
    application.Unload(TimeSpan.FromSeconds(5));  
}  
catch (TimeoutException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
## <a name="resuming-a-workflow"></a><span data-ttu-id="e8c20-107">Reanudar un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e8c20-107">Resuming a Workflow</span></span>  

 <span data-ttu-id="e8c20-108">Para reanudar un flujo de trabajo previamente pausado y descargado, utilice <xref:System.Activities.WorkflowApplication.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="e8c20-108">To resume a previously paused and unloaded workflow, use <xref:System.Activities.WorkflowApplication.Load%2A>.</span></span> <span data-ttu-id="e8c20-109">Este método carga un flujo de trabajo en la memoria desde un almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="e8c20-109">This method loads a workflow from a persistence store into memory.</span></span>  
  
```csharp  
WorkflowApplication application = new WorkflowApplication(activity);  
application.InstanceStore = instanceStore;  
application.Load(id);  
```  
  
## <a name="example"></a><span data-ttu-id="e8c20-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e8c20-110">Example</span></span>  

 <span data-ttu-id="e8c20-111">El siguiente ejemplo de código muestra cómo pausar y reanudar un flujo de trabajo utilizando la persistencia.</span><span class="sxs-lookup"><span data-stu-id="e8c20-111">The following code sample demonstrates how to pause and resume a workflow by using persistence.</span></span>  
  
```csharp  
static string bkName = "bkName";  
static void Main(string[] args)
{  
    StartAndUnloadInstance();  
}  
  
static void StartAndUnloadInstance()
{  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    SqlWorkflowInstanceStore instanceStore = SetupSqlpersistenceStore();  
    wfApp.InstanceStore = instanceStore;  
    wfApp.Extensions.Add(SetupMyFileTrackingParticipant);  
    wfApp.PersistableIdle = (e) => {          ///persists application state and remove it from memory
    return PersistableIdleAction.Unload;  
    };  
    wfApp.Unloaded = (e) => {  
        waitHandler.Set();  
    };  
    Guid id = wfApp.Id;  
    wfApp.Run();  
    waitHandler.WaitOne();  
    LoadAndCompleteInstance(id);  
}  
  
static void LoadAndCompleteInstance(Guid id)
{
    Console.WriteLine("Press <enter> to load the persisted workflow");  
    Console.ReadLine();  
    AutoResetEvent waitHandler = new AutoResetEvent(false);  
    WorkflowApplication wfApp = new WorkflowApplication(GetDelayedWF());  
    wfApp.InstanceStore =  
        new SqlWorkflowInstanceStore(ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString());  
    wfApp.Completed = (workflowApplicationCompletedEventArgs) => {  
        Console.WriteLine("\nWorkflowApplication has Completed in the {0} state.",  
            workflowApplicationCompletedEventArgs.CompletionState);  
    };  
    wfApp.Unloaded = (workflowApplicationEventArgs) => {  
        Console.WriteLine("WorkflowApplication has Unloaded\n");  
        waitHandler.Set();  
    };  
    wfApp.Load(id);  
    wfApp.Run();  
    waitHandler.WaitOne();  
}  
  
public static Activity GetDelayedWF()
{  
    return new Sequence {  
        Activities ={  
            new WriteLine{Text="Workflow Started"},  
            new Delay{Duration=TimeSpan.FromSeconds(10)},  
            new WriteLine{Text="Workflow Ended"}  
        }  
    };  
}  
  
private static SqlWorkflowInstanceStore SetupSqlpersistenceStore()
{
     string connectionString = ConfigurationManager.AppSettings["SqlWF4PersistenceConnectionString"].ToString();  
    SqlWorkflowInstanceStore sqlWFInstanceStore = new SqlWorkflowInstanceStore(connectionString);  
    sqlWFInstanceStore.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;  
    InstanceHandle handle = sqlWFInstanceStore.CreateInstanceHandle();  
    InstanceView view = sqlWFInstanceStore.Execute(handle, new CreateWorkflowOwnerCommand(), TimeSpan.FromSeconds(5));  
    handle.Free();  
    sqlWFInstanceStore.DefaultInstanceOwner = view.InstanceOwner;  
    return sqlWFInstanceStore;  
}  
```
