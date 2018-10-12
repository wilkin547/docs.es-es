---
title: '&lt;state&gt; de WCF, &lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 427cba7a51bfb908171e476cd703c6a40fd6e144
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123220"
---
# <a name="ltstategt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="062a3-102">&lt;state&gt; de WCF, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="062a3-102">&lt;state&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="062a3-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="062a3-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="062a3-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="062a3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="062a3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="062a3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="062a3-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="062a3-106">\<tracking></span></span>  
<span data-ttu-id="062a3-107">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="062a3-107">\<profiles></span></span>  
<span data-ttu-id="062a3-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="062a3-108">\<trackingProfile></span></span>  
<span data-ttu-id="062a3-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="062a3-109">\<workflow></span></span>  
<span data-ttu-id="062a3-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="062a3-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="062a3-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="062a3-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="062a3-112">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="062a3-112">\<states></span></span>  
<span data-ttu-id="062a3-113">\<estado ></span><span class="sxs-lookup"><span data-stu-id="062a3-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="062a3-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="062a3-114">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="062a3-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="062a3-115">Attributes and elements</span></span>

<span data-ttu-id="062a3-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="062a3-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="062a3-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="062a3-117">Attributes</span></span>

|<span data-ttu-id="062a3-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="062a3-118">Attribute</span></span>|<span data-ttu-id="062a3-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="062a3-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="062a3-120">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="062a3-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="062a3-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="062a3-121">Child elements</span></span>

<span data-ttu-id="062a3-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="062a3-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="062a3-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="062a3-123">Parent elements</span></span>

|<span data-ttu-id="062a3-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="062a3-124">Element</span></span>|<span data-ttu-id="062a3-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="062a3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="062a3-126">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="062a3-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="062a3-127">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="062a3-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="062a3-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="062a3-128">Remarks</span></span>  

<span data-ttu-id="062a3-129">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="062a3-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="062a3-130">Los valores de estado posibles se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="062a3-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="062a3-131">Estado</span><span class="sxs-lookup"><span data-stu-id="062a3-131">State</span></span>|<span data-ttu-id="062a3-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="062a3-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="062a3-133">Anulado</span><span class="sxs-lookup"><span data-stu-id="062a3-133">Aborted</span></span>|<span data-ttu-id="062a3-134">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="062a3-135">Completado</span><span class="sxs-lookup"><span data-stu-id="062a3-135">Completed</span></span>|<span data-ttu-id="062a3-136">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="062a3-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="062a3-137">Deleted</span></span>|<span data-ttu-id="062a3-138">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="062a3-139">Inactivo</span><span class="sxs-lookup"><span data-stu-id="062a3-139">Idle</span></span>|<span data-ttu-id="062a3-140">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="062a3-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="062a3-141">Conservado</span><span class="sxs-lookup"><span data-stu-id="062a3-141">Persisted</span></span>|<span data-ttu-id="062a3-142">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="062a3-143">Reanudado</span><span class="sxs-lookup"><span data-stu-id="062a3-143">Resumed</span></span>|<span data-ttu-id="062a3-144">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="062a3-145">Comenzado</span><span class="sxs-lookup"><span data-stu-id="062a3-145">Started</span></span>|<span data-ttu-id="062a3-146">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="062a3-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="062a3-147">UnhandledException</span></span>|<span data-ttu-id="062a3-148">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="062a3-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="062a3-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="062a3-149">Unloaded</span></span>|<span data-ttu-id="062a3-150">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="062a3-151">Cancelado</span><span class="sxs-lookup"><span data-stu-id="062a3-151">Canceled</span></span>|<span data-ttu-id="062a3-152">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="062a3-153">Suspendido</span><span class="sxs-lookup"><span data-stu-id="062a3-153">Suspended</span></span>|<span data-ttu-id="062a3-154">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="062a3-155">Terminado</span><span class="sxs-lookup"><span data-stu-id="062a3-155">Terminated</span></span>|<span data-ttu-id="062a3-156">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="062a3-157">No suspendido</span><span class="sxs-lookup"><span data-stu-id="062a3-157">Unsuspended</span></span>|<span data-ttu-id="062a3-158">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="062a3-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="062a3-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="062a3-159">Example</span></span>

<span data-ttu-id="062a3-160">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="062a3-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml
<workflowInstanceQueries>
  <workflowInstanceQuery>  
    <states>  
      <state name="Started"/>  
    </states>  
  </workflowInstanceQuery>  
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="062a3-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="062a3-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="062a3-162">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="062a3-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="062a3-163">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="062a3-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
