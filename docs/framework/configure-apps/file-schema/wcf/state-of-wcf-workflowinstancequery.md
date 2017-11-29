---
title: '&lt;state&gt; de WCF, &lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e26a55323ceedd06ceadbee6d993306411aa114a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="f46e5-102">&lt;state&gt; de WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="f46e5-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="f46e5-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f46e5-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="f46e5-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f46e5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f46e5-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f46e5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f46e5-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="f46e5-106">\<tracking></span></span>  
<span data-ttu-id="f46e5-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f46e5-107">\<trackingProfile></span></span>  
<span data-ttu-id="f46e5-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f46e5-108">\<workflow></span></span>  
<span data-ttu-id="f46e5-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="f46e5-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="f46e5-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f46e5-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="f46e5-111">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="f46e5-111">\<states></span></span>  
<span data-ttu-id="f46e5-112">\<estado ></span><span class="sxs-lookup"><span data-stu-id="f46e5-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f46e5-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f46e5-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f46e5-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f46e5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="f46e5-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f46e5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f46e5-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="f46e5-116">Attributes</span></span>  
  
|<span data-ttu-id="f46e5-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="f46e5-117">Attribute</span></span>|<span data-ttu-id="f46e5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46e5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f46e5-119">name</span><span class="sxs-lookup"><span data-stu-id="f46e5-119">name</span></span>|<span data-ttu-id="f46e5-120">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f46e5-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f46e5-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f46e5-121">Child Elements</span></span>  
 <span data-ttu-id="f46e5-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f46e5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f46e5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f46e5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f46e5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f46e5-124">Element</span></span>|<span data-ttu-id="f46e5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46e5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f46e5-126">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="f46e5-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="f46e5-127">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f46e5-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f46e5-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f46e5-128">Remarks</span></span>  
 <span data-ttu-id="f46e5-129">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="f46e5-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="f46e5-130">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="f46e5-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="f46e5-131">Estado</span><span class="sxs-lookup"><span data-stu-id="f46e5-131">State</span></span>|<span data-ttu-id="f46e5-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46e5-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f46e5-133">Anulado</span><span class="sxs-lookup"><span data-stu-id="f46e5-133">Aborted</span></span>|<span data-ttu-id="f46e5-134">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="f46e5-135">Completado</span><span class="sxs-lookup"><span data-stu-id="f46e5-135">Completed</span></span>|<span data-ttu-id="f46e5-136">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="f46e5-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="f46e5-137">Deleted</span></span>|<span data-ttu-id="f46e5-138">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="f46e5-139">Inactivo</span><span class="sxs-lookup"><span data-stu-id="f46e5-139">Idle</span></span>|<span data-ttu-id="f46e5-140">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="f46e5-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="f46e5-141">Conservado</span><span class="sxs-lookup"><span data-stu-id="f46e5-141">Persisted</span></span>|<span data-ttu-id="f46e5-142">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="f46e5-143">Reanudado</span><span class="sxs-lookup"><span data-stu-id="f46e5-143">Resumed</span></span>|<span data-ttu-id="f46e5-144">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="f46e5-145">Comenzado</span><span class="sxs-lookup"><span data-stu-id="f46e5-145">Started</span></span>|<span data-ttu-id="f46e5-146">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="f46e5-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="f46e5-147">UnhandledException</span></span>|<span data-ttu-id="f46e5-148">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="f46e5-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="f46e5-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="f46e5-149">Unloaded</span></span>|<span data-ttu-id="f46e5-150">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="f46e5-151">Cancelado</span><span class="sxs-lookup"><span data-stu-id="f46e5-151">Canceled</span></span>|<span data-ttu-id="f46e5-152">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="f46e5-153">Suspendido</span><span class="sxs-lookup"><span data-stu-id="f46e5-153">Suspended</span></span>|<span data-ttu-id="f46e5-154">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="f46e5-155">Terminado</span><span class="sxs-lookup"><span data-stu-id="f46e5-155">Terminated</span></span>|<span data-ttu-id="f46e5-156">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="f46e5-157">No suspendido</span><span class="sxs-lookup"><span data-stu-id="f46e5-157">Unsuspended</span></span>|<span data-ttu-id="f46e5-158">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f46e5-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f46e5-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f46e5-159">Example</span></span>  
 <span data-ttu-id="f46e5-160">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="f46e5-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f46e5-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="f46e5-161">See Also</span></span>  
 <span data-ttu-id="f46e5-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f46e5-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f46e5-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f46e5-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f46e5-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f46e5-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f46e5-165">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f46e5-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f46e5-166">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f46e5-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
