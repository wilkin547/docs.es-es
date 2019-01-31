---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 38b0522b93c051473d7cdc28ae955cc3b7b58efe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287240"
---
# <a name="state"></a><span data-ttu-id="3a43a-101">\<state></span><span class="sxs-lookup"><span data-stu-id="3a43a-101">\<state></span></span>
<span data-ttu-id="3a43a-102">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3a43a-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="3a43a-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3a43a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3a43a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3a43a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3a43a-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3a43a-105">\<tracking></span></span>  
<span data-ttu-id="3a43a-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3a43a-106">\<trackingProfile></span></span>  
<span data-ttu-id="3a43a-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3a43a-107">\<workflow></span></span>  
<span data-ttu-id="3a43a-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="3a43a-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="3a43a-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="3a43a-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="3a43a-110">\<states></span><span class="sxs-lookup"><span data-stu-id="3a43a-110">\<states></span></span>  
<span data-ttu-id="3a43a-111">\<state></span><span class="sxs-lookup"><span data-stu-id="3a43a-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a43a-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a43a-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a43a-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a43a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3a43a-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a43a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a43a-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a43a-115">Attributes</span></span>  
  
|<span data-ttu-id="3a43a-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3a43a-116">Attribute</span></span>|<span data-ttu-id="3a43a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a43a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a43a-118">name</span><span class="sxs-lookup"><span data-stu-id="3a43a-118">name</span></span>|<span data-ttu-id="3a43a-119">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3a43a-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a43a-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a43a-120">Child Elements</span></span>  
 <span data-ttu-id="3a43a-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a43a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a43a-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a43a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3a43a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a43a-123">Element</span></span>|<span data-ttu-id="3a43a-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a43a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a43a-125">\<states></span><span class="sxs-lookup"><span data-stu-id="3a43a-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3a43a-126">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3a43a-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a43a-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a43a-127">Remarks</span></span>  
 <span data-ttu-id="3a43a-128">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="3a43a-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="3a43a-129">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="3a43a-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="3a43a-130">Estado</span><span class="sxs-lookup"><span data-stu-id="3a43a-130">State</span></span>|<span data-ttu-id="3a43a-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a43a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3a43a-132">Anulado</span><span class="sxs-lookup"><span data-stu-id="3a43a-132">Aborted</span></span>|<span data-ttu-id="3a43a-133">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="3a43a-134">Completado</span><span class="sxs-lookup"><span data-stu-id="3a43a-134">Completed</span></span>|<span data-ttu-id="3a43a-135">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="3a43a-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="3a43a-136">Deleted</span></span>|<span data-ttu-id="3a43a-137">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="3a43a-138">Inactivo</span><span class="sxs-lookup"><span data-stu-id="3a43a-138">Idle</span></span>|<span data-ttu-id="3a43a-139">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="3a43a-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="3a43a-140">Conservado</span><span class="sxs-lookup"><span data-stu-id="3a43a-140">Persisted</span></span>|<span data-ttu-id="3a43a-141">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="3a43a-142">Reanudado</span><span class="sxs-lookup"><span data-stu-id="3a43a-142">Resumed</span></span>|<span data-ttu-id="3a43a-143">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="3a43a-144">Comenzado</span><span class="sxs-lookup"><span data-stu-id="3a43a-144">Started</span></span>|<span data-ttu-id="3a43a-145">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="3a43a-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="3a43a-146">UnhandledException</span></span>|<span data-ttu-id="3a43a-147">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="3a43a-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="3a43a-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="3a43a-148">Unloaded</span></span>|<span data-ttu-id="3a43a-149">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="3a43a-150">Cancelado</span><span class="sxs-lookup"><span data-stu-id="3a43a-150">Canceled</span></span>|<span data-ttu-id="3a43a-151">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="3a43a-152">Suspendido</span><span class="sxs-lookup"><span data-stu-id="3a43a-152">Suspended</span></span>|<span data-ttu-id="3a43a-153">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="3a43a-154">Terminado</span><span class="sxs-lookup"><span data-stu-id="3a43a-154">Terminated</span></span>|<span data-ttu-id="3a43a-155">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="3a43a-156">No suspendido</span><span class="sxs-lookup"><span data-stu-id="3a43a-156">Unsuspended</span></span>|<span data-ttu-id="3a43a-157">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a43a-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3a43a-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a43a-158">Example</span></span>  
 <span data-ttu-id="3a43a-159">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="3a43a-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a43a-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a43a-160">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a43a-161">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3a43a-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a43a-162">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3a43a-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
