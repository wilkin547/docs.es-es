---
title: <state>de WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854952"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="22e05-102">\<> de estado de WCF \<, workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="22e05-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="22e05-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22e05-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="22e05-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="22e05-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="22e05-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="22e05-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="22e05-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="22e05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="22e05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="22e05-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="22e05-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="22e05-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="22e05-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQuery**](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="22e05-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Estados >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="22e05-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="22e05-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de estado**</span><span class="sxs-lookup"><span data-stu-id="22e05-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22e05-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22e05-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22e05-116">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22e05-116">Attributes and elements</span></span>

<span data-ttu-id="22e05-117">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22e05-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="22e05-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="22e05-118">Attributes</span></span>

|<span data-ttu-id="22e05-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="22e05-119">Attribute</span></span>|<span data-ttu-id="22e05-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="22e05-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="22e05-121">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22e05-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22e05-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22e05-122">Child elements</span></span>

<span data-ttu-id="22e05-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22e05-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="22e05-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22e05-124">Parent elements</span></span>

|<span data-ttu-id="22e05-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="22e05-125">Element</span></span>|<span data-ttu-id="22e05-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="22e05-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22e05-127">\<states></span><span class="sxs-lookup"><span data-stu-id="22e05-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="22e05-128">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22e05-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22e05-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22e05-129">Remarks</span></span>  

<span data-ttu-id="22e05-130">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="22e05-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="22e05-131">Los valores de estado posibles se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="22e05-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="22e05-132">Estado</span><span class="sxs-lookup"><span data-stu-id="22e05-132">State</span></span>|<span data-ttu-id="22e05-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="22e05-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="22e05-134">Anulado</span><span class="sxs-lookup"><span data-stu-id="22e05-134">Aborted</span></span>|<span data-ttu-id="22e05-135">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="22e05-136">Completada</span><span class="sxs-lookup"><span data-stu-id="22e05-136">Completed</span></span>|<span data-ttu-id="22e05-137">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="22e05-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="22e05-138">Deleted</span></span>|<span data-ttu-id="22e05-139">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="22e05-140">Inactivo</span><span class="sxs-lookup"><span data-stu-id="22e05-140">Idle</span></span>|<span data-ttu-id="22e05-141">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="22e05-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="22e05-142">Conservado</span><span class="sxs-lookup"><span data-stu-id="22e05-142">Persisted</span></span>|<span data-ttu-id="22e05-143">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="22e05-144">Reanudado</span><span class="sxs-lookup"><span data-stu-id="22e05-144">Resumed</span></span>|<span data-ttu-id="22e05-145">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="22e05-146">Started</span><span class="sxs-lookup"><span data-stu-id="22e05-146">Started</span></span>|<span data-ttu-id="22e05-147">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="22e05-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="22e05-148">UnhandledException</span></span>|<span data-ttu-id="22e05-149">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="22e05-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="22e05-150">Descargado</span><span class="sxs-lookup"><span data-stu-id="22e05-150">Unloaded</span></span>|<span data-ttu-id="22e05-151">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="22e05-152">Cancelado</span><span class="sxs-lookup"><span data-stu-id="22e05-152">Canceled</span></span>|<span data-ttu-id="22e05-153">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="22e05-154">Suspendido</span><span class="sxs-lookup"><span data-stu-id="22e05-154">Suspended</span></span>|<span data-ttu-id="22e05-155">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="22e05-156">Terminado</span><span class="sxs-lookup"><span data-stu-id="22e05-156">Terminated</span></span>|<span data-ttu-id="22e05-157">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="22e05-158">No suspendido</span><span class="sxs-lookup"><span data-stu-id="22e05-158">Unsuspended</span></span>|<span data-ttu-id="22e05-159">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="22e05-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="22e05-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22e05-160">Example</span></span>

<span data-ttu-id="22e05-161">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="22e05-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="22e05-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="22e05-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="22e05-163">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="22e05-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="22e05-164">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="22e05-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
