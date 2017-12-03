---
title: Instancias de flujo de trabajo no persistentes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e01af77-6b14-4964-91a5-7dfd143449c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a7dd9e0ccc29c81426064110eda3e00d2f27b99
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="non-persisted-workflow-instances"></a><span data-ttu-id="bbd32-102">Instancias de flujo de trabajo no persistentes</span><span class="sxs-lookup"><span data-stu-id="bbd32-102">Non-Persisted Workflow Instances</span></span>
<span data-ttu-id="bbd32-103">Cuando se crea una nueva instancia de un flujo de trabajo cuyo estado persiste en <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, el host del servicio crea una entrada inicial para ese servicio en el almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="bbd32-103">When a new instance of a workflow is created that persists its state in the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, the service host creates an entry for that service in the instance store.</span></span> <span data-ttu-id="bbd32-104">Posteriormente, cuando la instancia de flujo de trabajo persiste por primera vez, <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> almacena el estado de la instancia actual.</span><span class="sxs-lookup"><span data-stu-id="bbd32-104">Subsequently, when the workflow instance is persisted for the first time, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> stores the current instance state.</span></span> <span data-ttu-id="bbd32-105">Si el flujo de trabajo se hospeda en el Servicio de activación de procesos de Windows, los datos de implementación del servicio también se escriben en el almacén de la instancia cuando la instancia persiste por primera vez.</span><span class="sxs-lookup"><span data-stu-id="bbd32-105">If the workflow is hosted in the Windows Process Activation Service, the service deployment data is also written to the instance store when the instance is persisted for the first time.</span></span>  
  
 <span data-ttu-id="bbd32-106">Siempre y cuando la instancia de flujo de trabajo no ha persistido, está en un **no persistentes** estado.</span><span class="sxs-lookup"><span data-stu-id="bbd32-106">As long as the workflow instance has not been persisted, it is in a **non-persisted** state.</span></span> <span data-ttu-id="bbd32-107">Mientras se encuentra en este estado, la instancia de flujo de trabajo no se puede recuperar después de un reciclaje del dominio de aplicación, error del host o error del equipo.</span><span class="sxs-lookup"><span data-stu-id="bbd32-107">While in this state, the workflow instance cannot be recovered after an application domain recycle, host failure, or computer failure.</span></span>  
  
## <a name="the-non-persisted-state"></a><span data-ttu-id="bbd32-108">El estado no persistente</span><span class="sxs-lookup"><span data-stu-id="bbd32-108">The Non-Persisted State</span></span>  
 <span data-ttu-id="bbd32-109">Las instancias del flujo de trabajo que no han persistido permanecen en un estado no persistente en los siguientes casos:</span><span class="sxs-lookup"><span data-stu-id="bbd32-109">Durable workflow instances that have not been persisted remain in a non-persisted state in the following cases:</span></span>  
  
-   <span data-ttu-id="bbd32-110">El host del servicio se bloquea antes de que la instancia de flujo de trabajo se guarde por primera vez.</span><span class="sxs-lookup"><span data-stu-id="bbd32-110">The service host crashes before the workflow instance is persisted for the first time.</span></span> <span data-ttu-id="bbd32-111">La instancia de flujo de trabajo permanece en el almacén de la instancia y no se recupera.</span><span class="sxs-lookup"><span data-stu-id="bbd32-111">The workflow instance remains in the instance store and is not recovered.</span></span> <span data-ttu-id="bbd32-112">Si llega un mensaje correlacionado, la instancia de flujo de trabajo se activa de nuevo.</span><span class="sxs-lookup"><span data-stu-id="bbd32-112">If a correlated message arrives, the workflow instance becomes active again.</span></span>  
  
-   <span data-ttu-id="bbd32-113">La instancia de flujo de trabajo experimenta una excepción antes de ser guardada por primera vez.</span><span class="sxs-lookup"><span data-stu-id="bbd32-113">The workflow instance experiences an exception before it is persisted for the first time.</span></span> <span data-ttu-id="bbd32-114">Dependiendo de lo que devolvió <xref:System.Activities.UnhandledExceptionAction>, se producen los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="bbd32-114">Depending on the <xref:System.Activities.UnhandledExceptionAction> returned, the following scenarios occur:</span></span>  
  
    -   <span data-ttu-id="bbd32-115"><xref:System.Activities.UnhandledExceptionAction> se establece en <xref:System.Activities.UnhandledExceptionAction.Abort>: cuando se produce una excepción, la información de la implementación del servicio se escribe en el almacén de la instancia y la instancia de flujo de trabajo se descarga desde la memoria.</span><span class="sxs-lookup"><span data-stu-id="bbd32-115"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Abort>: When an exception occurs, service deployment information is written to the instance store, and the workflow instance is unloaded from memory.</span></span> <span data-ttu-id="bbd32-116">La instancia de flujo de trabajo permanece en un estado no persistente y no se puede recargar.</span><span class="sxs-lookup"><span data-stu-id="bbd32-116">The workflow instance remains in a non-persisted state and cannot be reloaded.</span></span>  
  
    -   <span data-ttu-id="bbd32-117"><xref:System.Activities.UnhandledExceptionAction> se establece en <xref:System.Activities.UnhandledExceptionAction.Cancel> o en <xref:System.Activities.UnhandledExceptionAction.Terminate>: cuando se produce una excepción, la información de la implementación del servicio se escribe en el almacén de la instancia y la instancia de actividad se establece en <xref:System.Activities.ActivityInstanceState.Closed>.</span><span class="sxs-lookup"><span data-stu-id="bbd32-117"><xref:System.Activities.UnhandledExceptionAction> is set to <xref:System.Activities.UnhandledExceptionAction.Cancel> or <xref:System.Activities.UnhandledExceptionAction.Terminate>: When an exception occurs, service deployment information is written to the instance store, and the activity instance state is set to <xref:System.Activities.ActivityInstanceState.Closed>.</span></span>  
  
 <span data-ttu-id="bbd32-118">Para minimizar el riesgo de encontrar descargadas instancias de flujo de trabajo no persistentes, recomendamos conservar el flujo de trabajo temprano en su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="bbd32-118">To minimize the risk of encountering unloaded non-persisted workflow instances, we recommend persisting the workflow early in its life cycle.</span></span>  
  
## <a name="detection-and-removal-of-non-persisted-instances"></a><span data-ttu-id="bbd32-119">Detección y eliminación de instancias no persistentes</span><span class="sxs-lookup"><span data-stu-id="bbd32-119">Detection and Removal of Non-Persisted Instances</span></span>  
 <span data-ttu-id="bbd32-120"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> no quita cualquier  instancia de flujo de trabajo no persistente del almacén de la instancia.</span><span class="sxs-lookup"><span data-stu-id="bbd32-120">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> does not remove any non-persisted workflow instances from the instance store.</span></span> <span data-ttu-id="bbd32-121">Tampoco quita cualquier propietario de bloqueo caducado que esté asociado con instancias de flujo de trabajo no persistentes.</span><span class="sxs-lookup"><span data-stu-id="bbd32-121">It also does not remove any expired lock owners that have non-persisted workflow instances associated with them.</span></span>  
  
 <span data-ttu-id="bbd32-122">Recomendamos que el administrador compruebe periódicamente si hay instancias no persistentes en el almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="bbd32-122">We recommend that the administrator periodically checks the instance store for non-persisted instances.</span></span> <span data-ttu-id="bbd32-123">Los administradores pueden quitar esas instancias del almacén de instancias siempre que sepan que este flujo de trabajo no recibirá mensajes correlacionados.</span><span class="sxs-lookup"><span data-stu-id="bbd32-123">Administrators can remove those instances from the instance store as long as they know that this workflow will not receive correlated messages.</span></span> <span data-ttu-id="bbd32-124">Por ejemplo, si la instancia ha estado en la base de datos durante varios meses y sabe que por lo general el flujo de trabajo tiene una duración de varios días, se podría suponer que fue una instancia inicializada que fue bloqueada.</span><span class="sxs-lookup"><span data-stu-id="bbd32-124">For example, if the instance has been in the database for several months and it is known that the workflow typically has a lifetime of several days, it would be safe to assume that this was an initialized instance that had crashed.</span></span>  
  
 <span data-ttu-id="bbd32-125">Para encontrar instancias no persistentes en el almacén de instancias de flujo de trabajo de SQL, puede utilizar las siguientes consultas SQL:</span><span class="sxs-lookup"><span data-stu-id="bbd32-125">To find non-persisted instances in the SQL Workflow Instance Store you can use the following SQL queries:</span></span>  
  
-   <span data-ttu-id="bbd32-126">Esta consulta encuentra todas las instancias que no se han conservado y devuelve su identificador y hora de creación (almacenados en hora UTC).</span><span class="sxs-lookup"><span data-stu-id="bbd32-126">This query finds all instances that have not been persisted, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0  
    ```  
  
-   <span data-ttu-id="bbd32-127">Esta consulta encuentra todas las instancias que no se han conservado, y que no se han cargado, y devuelve su identificador y hora de creación (almacenados en hora UTC).</span><span class="sxs-lookup"><span data-stu-id="bbd32-127">This query finds all instances that have not been persisted, and that are not loaded, and returns the ID and creation time (stored in UTC time) for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and CurrentMachine is NULL  
    ```  
  
-   <span data-ttu-id="bbd32-128">Esta consulta encuentra todas las instancias suspendidas que no se han conservado, y que no se han cargado, y devuelve su identificador y hora de creación (almacenados en hora UTC), el motivo de la suspensión y el nombre de la excepción.</span><span class="sxs-lookup"><span data-stu-id="bbd32-128">This query finds all suspended instances that have not been persisted, and returns the ID, creation time (stored in UTC time), suspension reason, and exception name for them.</span></span>  
  
    ```sql  
    select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName   
        from [System.Activities.DurableInstancing].[Instances]   
        where IsInitialized = 0   
            and IsSuspended = 1  
    ```  
  
 <span data-ttu-id="bbd32-129">Tenga cuidado al eliminar instancias no persistentes.</span><span class="sxs-lookup"><span data-stu-id="bbd32-129">Use care when you are deleting non-persisted instances.</span></span> <span data-ttu-id="bbd32-130">En general, resulta seguro quitar instancias no persistentes creadas por <xref:System.ServiceModel.Activities.WorkflowServiceHost> que están suspendidas o que no se han cargado.</span><span class="sxs-lookup"><span data-stu-id="bbd32-130">In general, it is safe to remove non-persisted instances created by <xref:System.ServiceModel.Activities.WorkflowServiceHost> that are suspended or are not loaded.</span></span> <span data-ttu-id="bbd32-131">Esas instancias concretas se pueden eliminar del almacén eliminándolas de la vista `[System.Activities.DurableInstancing].[Instances]` mediante el siguiente comando SQL, sustituyendo el identificador de instancia correcto.</span><span class="sxs-lookup"><span data-stu-id="bbd32-131">Those specific instances can be deleted from the store by deleting them from the `[System.Activities.DurableInstancing].[Instances]` view by using the following SQL command, substituting the correct instance ID.</span></span>  
  
```sql  
delete [System.Activities.DurableInstancing].[Instances]   
    where InstanceId=’078a9bc4-ada5-4f9e-8cce-b0eb0009995f’  
```  
  
> [!WARNING]
>  <span data-ttu-id="bbd32-132">No recomendamos quitar todos instancias no persistentes, porque esto incluye instancias que se han creado recientemente y todavía no se han guardado.</span><span class="sxs-lookup"><span data-stu-id="bbd32-132">We do not recommend removing all non-persisted instances because this includes instances that have just been created and have not yet been persisted.</span></span>
