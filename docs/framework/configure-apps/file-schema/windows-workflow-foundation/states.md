---
title: '&lt;Estados&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="2f3f9-102">&lt;Estados&gt;</span><span class="sxs-lookup"><span data-stu-id="2f3f9-102">&lt;states&gt;</span></span>
<span data-ttu-id="2f3f9-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="2f3f9-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2f3f9-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2f3f9-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2f3f9-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-106">\<tracking></span></span>  
<span data-ttu-id="2f3f9-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-107">\<trackingProfile></span></span>  
<span data-ttu-id="2f3f9-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-108">\<workflow></span></span>  
<span data-ttu-id="2f3f9-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="2f3f9-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="2f3f9-111">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3f9-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f3f9-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f3f9-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2f3f9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2f3f9-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f3f9-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="2f3f9-115">Attributes</span></span>  
 <span data-ttu-id="2f3f9-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f3f9-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2f3f9-117">Child Elements</span></span>  
  
|<span data-ttu-id="2f3f9-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f3f9-118">Element</span></span>|<span data-ttu-id="2f3f9-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f9-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f3f9-120">\<estado ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2f3f9-121">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f3f9-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2f3f9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2f3f9-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="2f3f9-123">Element</span></span>|<span data-ttu-id="2f3f9-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f9-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2f3f9-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="2f3f9-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="2f3f9-126">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f3f9-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2f3f9-127">Remarks</span></span>  
 <span data-ttu-id="2f3f9-128">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="2f3f9-129">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="2f3f9-130">Estado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-130">State</span></span>|<span data-ttu-id="2f3f9-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="2f3f9-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2f3f9-132">Anulado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-132">Aborted</span></span>|<span data-ttu-id="2f3f9-133">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2f3f9-134">Completado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-134">Completed</span></span>|<span data-ttu-id="2f3f9-135">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="2f3f9-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="2f3f9-136">Deleted</span></span>|<span data-ttu-id="2f3f9-137">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="2f3f9-138">Inactivo</span><span class="sxs-lookup"><span data-stu-id="2f3f9-138">Idle</span></span>|<span data-ttu-id="2f3f9-139">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="2f3f9-140">Conservado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-140">Persisted</span></span>|<span data-ttu-id="2f3f9-141">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="2f3f9-142">Reanudado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-142">Resumed</span></span>|<span data-ttu-id="2f3f9-143">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="2f3f9-144">Comenzado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-144">Started</span></span>|<span data-ttu-id="2f3f9-145">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="2f3f9-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="2f3f9-146">UnhandledException</span></span>|<span data-ttu-id="2f3f9-147">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="2f3f9-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="2f3f9-148">Unloaded</span></span>|<span data-ttu-id="2f3f9-149">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="2f3f9-150">Cancelado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-150">Canceled</span></span>|<span data-ttu-id="2f3f9-151">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="2f3f9-152">Suspendido</span><span class="sxs-lookup"><span data-stu-id="2f3f9-152">Suspended</span></span>|<span data-ttu-id="2f3f9-153">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="2f3f9-154">Terminado</span><span class="sxs-lookup"><span data-stu-id="2f3f9-154">Terminated</span></span>|<span data-ttu-id="2f3f9-155">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="2f3f9-156">No suspendido</span><span class="sxs-lookup"><span data-stu-id="2f3f9-156">Unsuspended</span></span>|<span data-ttu-id="2f3f9-157">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2f3f9-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f3f9-158">Example</span></span>  
 <span data-ttu-id="2f3f9-159">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="2f3f9-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f3f9-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f3f9-160">See Also</span></span>  
 <span data-ttu-id="2f3f9-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2f3f9-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="2f3f9-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2f3f9-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="2f3f9-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2f3f9-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="2f3f9-164">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2f3f9-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2f3f9-165">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2f3f9-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
