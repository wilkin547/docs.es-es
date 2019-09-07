---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398617"
---
# <a name="states"></a><span data-ttu-id="0c419-101">\<states></span><span class="sxs-lookup"><span data-stu-id="0c419-101">\<states></span></span>
<span data-ttu-id="0c419-102">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c419-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="0c419-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0c419-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="0c419-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0c419-105">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="0c419-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="0c419-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="0c419-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="0c419-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="0c419-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="0c419-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="0c419-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Estados >**</span><span class="sxs-lookup"><span data-stu-id="0c419-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c419-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c419-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c419-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c419-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0c419-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c419-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c419-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c419-115">Attributes</span></span>  
 <span data-ttu-id="0c419-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0c419-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0c419-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c419-117">Child Elements</span></span>  
  
|<span data-ttu-id="0c419-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c419-118">Element</span></span>|<span data-ttu-id="0c419-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c419-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c419-120">\<state></span><span class="sxs-lookup"><span data-stu-id="0c419-120">\<state></span></span>](states.md)|<span data-ttu-id="0c419-121">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c419-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c419-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c419-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0c419-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c419-123">Element</span></span>|<span data-ttu-id="0c419-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c419-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c419-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="0c419-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="0c419-126">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="0c419-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c419-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c419-127">Remarks</span></span>  
 <span data-ttu-id="0c419-128">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="0c419-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="0c419-129">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="0c419-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="0c419-130">Estado</span><span class="sxs-lookup"><span data-stu-id="0c419-130">State</span></span>|<span data-ttu-id="0c419-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c419-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0c419-132">Anulado</span><span class="sxs-lookup"><span data-stu-id="0c419-132">Aborted</span></span>|<span data-ttu-id="0c419-133">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="0c419-134">Completada</span><span class="sxs-lookup"><span data-stu-id="0c419-134">Completed</span></span>|<span data-ttu-id="0c419-135">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="0c419-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="0c419-136">Deleted</span></span>|<span data-ttu-id="0c419-137">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="0c419-138">Inactivo</span><span class="sxs-lookup"><span data-stu-id="0c419-138">Idle</span></span>|<span data-ttu-id="0c419-139">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="0c419-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="0c419-140">Conservado</span><span class="sxs-lookup"><span data-stu-id="0c419-140">Persisted</span></span>|<span data-ttu-id="0c419-141">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="0c419-142">Reanudado</span><span class="sxs-lookup"><span data-stu-id="0c419-142">Resumed</span></span>|<span data-ttu-id="0c419-143">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="0c419-144">Started</span><span class="sxs-lookup"><span data-stu-id="0c419-144">Started</span></span>|<span data-ttu-id="0c419-145">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="0c419-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="0c419-146">UnhandledException</span></span>|<span data-ttu-id="0c419-147">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="0c419-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="0c419-148">Descargado</span><span class="sxs-lookup"><span data-stu-id="0c419-148">Unloaded</span></span>|<span data-ttu-id="0c419-149">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="0c419-150">Cancelado</span><span class="sxs-lookup"><span data-stu-id="0c419-150">Canceled</span></span>|<span data-ttu-id="0c419-151">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="0c419-152">Suspendido</span><span class="sxs-lookup"><span data-stu-id="0c419-152">Suspended</span></span>|<span data-ttu-id="0c419-153">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="0c419-154">Terminado</span><span class="sxs-lookup"><span data-stu-id="0c419-154">Terminated</span></span>|<span data-ttu-id="0c419-155">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="0c419-156">No suspendido</span><span class="sxs-lookup"><span data-stu-id="0c419-156">Unsuspended</span></span>|<span data-ttu-id="0c419-157">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c419-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0c419-158">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c419-158">Example</span></span>  
 <span data-ttu-id="0c419-159">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="0c419-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c419-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c419-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0c419-161">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c419-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0c419-162">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0c419-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
