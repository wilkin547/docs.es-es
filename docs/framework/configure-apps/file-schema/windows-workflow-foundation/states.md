---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797805"
---
# <a name="states"></a><span data-ttu-id="97b1b-101">\<states></span><span class="sxs-lookup"><span data-stu-id="97b1b-101">\<states></span></span>
<span data-ttu-id="97b1b-102">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="97b1b-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="97b1b-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="97b1b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="97b1b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="97b1b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="97b1b-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="97b1b-105">\<tracking></span></span>  
<span data-ttu-id="97b1b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="97b1b-106">\<trackingProfile></span></span>  
<span data-ttu-id="97b1b-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="97b1b-107">\<workflow></span></span>  
<span data-ttu-id="97b1b-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="97b1b-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="97b1b-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="97b1b-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="97b1b-110">\<states></span><span class="sxs-lookup"><span data-stu-id="97b1b-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b1b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97b1b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97b1b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97b1b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97b1b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97b1b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97b1b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="97b1b-114">Attributes</span></span>  
 <span data-ttu-id="97b1b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97b1b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97b1b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97b1b-116">Child Elements</span></span>  
  
|<span data-ttu-id="97b1b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="97b1b-117">Element</span></span>|<span data-ttu-id="97b1b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="97b1b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b1b-119">\<state></span><span class="sxs-lookup"><span data-stu-id="97b1b-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="97b1b-120">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="97b1b-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97b1b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97b1b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97b1b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="97b1b-122">Element</span></span>|<span data-ttu-id="97b1b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="97b1b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97b1b-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="97b1b-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="97b1b-125">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="97b1b-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97b1b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97b1b-126">Remarks</span></span>  
 <span data-ttu-id="97b1b-127">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="97b1b-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="97b1b-128">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="97b1b-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="97b1b-129">Estado</span><span class="sxs-lookup"><span data-stu-id="97b1b-129">State</span></span>|<span data-ttu-id="97b1b-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="97b1b-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="97b1b-131">Anulado</span><span class="sxs-lookup"><span data-stu-id="97b1b-131">Aborted</span></span>|<span data-ttu-id="97b1b-132">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="97b1b-133">Completada</span><span class="sxs-lookup"><span data-stu-id="97b1b-133">Completed</span></span>|<span data-ttu-id="97b1b-134">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="97b1b-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="97b1b-135">Deleted</span></span>|<span data-ttu-id="97b1b-136">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="97b1b-137">Inactivo</span><span class="sxs-lookup"><span data-stu-id="97b1b-137">Idle</span></span>|<span data-ttu-id="97b1b-138">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="97b1b-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="97b1b-139">Conservado</span><span class="sxs-lookup"><span data-stu-id="97b1b-139">Persisted</span></span>|<span data-ttu-id="97b1b-140">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="97b1b-141">Reanudado</span><span class="sxs-lookup"><span data-stu-id="97b1b-141">Resumed</span></span>|<span data-ttu-id="97b1b-142">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="97b1b-143">Comenzado</span><span class="sxs-lookup"><span data-stu-id="97b1b-143">Started</span></span>|<span data-ttu-id="97b1b-144">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="97b1b-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="97b1b-145">UnhandledException</span></span>|<span data-ttu-id="97b1b-146">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="97b1b-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="97b1b-147">Descargado</span><span class="sxs-lookup"><span data-stu-id="97b1b-147">Unloaded</span></span>|<span data-ttu-id="97b1b-148">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="97b1b-149">Cancelado</span><span class="sxs-lookup"><span data-stu-id="97b1b-149">Canceled</span></span>|<span data-ttu-id="97b1b-150">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="97b1b-151">Suspendido</span><span class="sxs-lookup"><span data-stu-id="97b1b-151">Suspended</span></span>|<span data-ttu-id="97b1b-152">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="97b1b-153">Terminado</span><span class="sxs-lookup"><span data-stu-id="97b1b-153">Terminated</span></span>|<span data-ttu-id="97b1b-154">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="97b1b-155">No suspendido</span><span class="sxs-lookup"><span data-stu-id="97b1b-155">Unsuspended</span></span>|<span data-ttu-id="97b1b-156">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97b1b-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="97b1b-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="97b1b-157">Example</span></span>  
 <span data-ttu-id="97b1b-158">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="97b1b-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="97b1b-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b1b-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="97b1b-160">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="97b1b-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="97b1b-161">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="97b1b-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
