---
title: '&lt;states&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: d1ec35b1c434b8188fde7b546e2dee42a93f5c91
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550583"
---
# <a name="ltstatesgt"></a><span data-ttu-id="14baa-102">&lt;states&gt;</span><span class="sxs-lookup"><span data-stu-id="14baa-102">&lt;states&gt;</span></span>
<span data-ttu-id="14baa-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="14baa-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="14baa-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="14baa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="14baa-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="14baa-105">\<system.serviceModel></span></span>  
<span data-ttu-id="14baa-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="14baa-106">\<tracking></span></span>  
<span data-ttu-id="14baa-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="14baa-107">\<trackingProfile></span></span>  
<span data-ttu-id="14baa-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="14baa-108">\<workflow></span></span>  
<span data-ttu-id="14baa-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="14baa-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="14baa-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="14baa-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="14baa-111">\<states></span><span class="sxs-lookup"><span data-stu-id="14baa-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14baa-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14baa-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14baa-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="14baa-113">Attributes and Elements</span></span>  
 <span data-ttu-id="14baa-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="14baa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14baa-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="14baa-115">Attributes</span></span>  
 <span data-ttu-id="14baa-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="14baa-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="14baa-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="14baa-117">Child Elements</span></span>  
  
|<span data-ttu-id="14baa-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="14baa-118">Element</span></span>|<span data-ttu-id="14baa-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="14baa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14baa-120">\<state></span><span class="sxs-lookup"><span data-stu-id="14baa-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="14baa-121">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="14baa-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="14baa-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="14baa-122">Parent Elements</span></span>  
  
|<span data-ttu-id="14baa-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="14baa-123">Element</span></span>|<span data-ttu-id="14baa-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="14baa-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14baa-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="14baa-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="14baa-126">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="14baa-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14baa-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14baa-127">Remarks</span></span>  
 <span data-ttu-id="14baa-128">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="14baa-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="14baa-129">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="14baa-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="14baa-130">Estado</span><span class="sxs-lookup"><span data-stu-id="14baa-130">State</span></span>|<span data-ttu-id="14baa-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="14baa-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="14baa-132">Anulado</span><span class="sxs-lookup"><span data-stu-id="14baa-132">Aborted</span></span>|<span data-ttu-id="14baa-133">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="14baa-134">Completado</span><span class="sxs-lookup"><span data-stu-id="14baa-134">Completed</span></span>|<span data-ttu-id="14baa-135">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="14baa-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="14baa-136">Deleted</span></span>|<span data-ttu-id="14baa-137">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="14baa-138">Inactivo</span><span class="sxs-lookup"><span data-stu-id="14baa-138">Idle</span></span>|<span data-ttu-id="14baa-139">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="14baa-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="14baa-140">Conservado</span><span class="sxs-lookup"><span data-stu-id="14baa-140">Persisted</span></span>|<span data-ttu-id="14baa-141">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="14baa-142">Reanudado</span><span class="sxs-lookup"><span data-stu-id="14baa-142">Resumed</span></span>|<span data-ttu-id="14baa-143">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="14baa-144">Comenzado</span><span class="sxs-lookup"><span data-stu-id="14baa-144">Started</span></span>|<span data-ttu-id="14baa-145">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="14baa-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="14baa-146">UnhandledException</span></span>|<span data-ttu-id="14baa-147">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="14baa-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="14baa-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="14baa-148">Unloaded</span></span>|<span data-ttu-id="14baa-149">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="14baa-150">Cancelado</span><span class="sxs-lookup"><span data-stu-id="14baa-150">Canceled</span></span>|<span data-ttu-id="14baa-151">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="14baa-152">Suspendido</span><span class="sxs-lookup"><span data-stu-id="14baa-152">Suspended</span></span>|<span data-ttu-id="14baa-153">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="14baa-154">Terminado</span><span class="sxs-lookup"><span data-stu-id="14baa-154">Terminated</span></span>|<span data-ttu-id="14baa-155">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="14baa-156">No suspendido</span><span class="sxs-lookup"><span data-stu-id="14baa-156">Unsuspended</span></span>|<span data-ttu-id="14baa-157">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="14baa-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="14baa-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14baa-158">Example</span></span>  
 <span data-ttu-id="14baa-159">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="14baa-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14baa-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="14baa-160">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="14baa-161">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="14baa-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="14baa-162">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="14baa-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
