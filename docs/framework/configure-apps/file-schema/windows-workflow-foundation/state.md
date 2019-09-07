---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398637"
---
# <a name="state"></a><span data-ttu-id="74ee9-101">\<> de estado</span><span class="sxs-lookup"><span data-stu-id="74ee9-101">\<state></span></span>
<span data-ttu-id="74ee9-102">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="74ee9-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="74ee9-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="74ee9-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="74ee9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="74ee9-105">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="74ee9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="74ee9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="74ee9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="74ee9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="74ee9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="74ee9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Estados >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="74ee9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="74ee9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de estado**</span><span class="sxs-lookup"><span data-stu-id="74ee9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74ee9-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74ee9-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="74ee9-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="74ee9-114">Attributes and Elements</span></span>  
 <span data-ttu-id="74ee9-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="74ee9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="74ee9-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="74ee9-116">Attributes</span></span>  
  
|<span data-ttu-id="74ee9-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="74ee9-117">Attribute</span></span>|<span data-ttu-id="74ee9-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74ee9-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="74ee9-119">name</span><span class="sxs-lookup"><span data-stu-id="74ee9-119">name</span></span>|<span data-ttu-id="74ee9-120">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="74ee9-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="74ee9-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="74ee9-121">Child Elements</span></span>  
 <span data-ttu-id="74ee9-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="74ee9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="74ee9-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="74ee9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="74ee9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="74ee9-124">Element</span></span>|<span data-ttu-id="74ee9-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74ee9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="74ee9-126">\<states></span><span class="sxs-lookup"><span data-stu-id="74ee9-126">\<states></span></span>](states.md)|<span data-ttu-id="74ee9-127">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="74ee9-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74ee9-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74ee9-128">Remarks</span></span>  
 <span data-ttu-id="74ee9-129">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="74ee9-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="74ee9-130">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="74ee9-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="74ee9-131">Estado</span><span class="sxs-lookup"><span data-stu-id="74ee9-131">State</span></span>|<span data-ttu-id="74ee9-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="74ee9-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="74ee9-133">Anulado</span><span class="sxs-lookup"><span data-stu-id="74ee9-133">Aborted</span></span>|<span data-ttu-id="74ee9-134">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="74ee9-135">Completada</span><span class="sxs-lookup"><span data-stu-id="74ee9-135">Completed</span></span>|<span data-ttu-id="74ee9-136">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="74ee9-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="74ee9-137">Deleted</span></span>|<span data-ttu-id="74ee9-138">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="74ee9-139">Inactivo</span><span class="sxs-lookup"><span data-stu-id="74ee9-139">Idle</span></span>|<span data-ttu-id="74ee9-140">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="74ee9-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="74ee9-141">Conservado</span><span class="sxs-lookup"><span data-stu-id="74ee9-141">Persisted</span></span>|<span data-ttu-id="74ee9-142">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="74ee9-143">Reanudado</span><span class="sxs-lookup"><span data-stu-id="74ee9-143">Resumed</span></span>|<span data-ttu-id="74ee9-144">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="74ee9-145">Started</span><span class="sxs-lookup"><span data-stu-id="74ee9-145">Started</span></span>|<span data-ttu-id="74ee9-146">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="74ee9-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="74ee9-147">UnhandledException</span></span>|<span data-ttu-id="74ee9-148">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="74ee9-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="74ee9-149">Descargado</span><span class="sxs-lookup"><span data-stu-id="74ee9-149">Unloaded</span></span>|<span data-ttu-id="74ee9-150">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="74ee9-151">Cancelado</span><span class="sxs-lookup"><span data-stu-id="74ee9-151">Canceled</span></span>|<span data-ttu-id="74ee9-152">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="74ee9-153">Suspendido</span><span class="sxs-lookup"><span data-stu-id="74ee9-153">Suspended</span></span>|<span data-ttu-id="74ee9-154">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="74ee9-155">Terminado</span><span class="sxs-lookup"><span data-stu-id="74ee9-155">Terminated</span></span>|<span data-ttu-id="74ee9-156">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="74ee9-157">No suspendido</span><span class="sxs-lookup"><span data-stu-id="74ee9-157">Unsuspended</span></span>|<span data-ttu-id="74ee9-158">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="74ee9-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="74ee9-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74ee9-159">Example</span></span>  
 <span data-ttu-id="74ee9-160">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="74ee9-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74ee9-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="74ee9-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="74ee9-162">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="74ee9-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="74ee9-163">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="74ee9-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
