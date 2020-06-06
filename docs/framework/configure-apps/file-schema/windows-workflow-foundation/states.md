---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398617"
---
# \<states>
<span data-ttu-id="d8cc2-101">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="d8cc2-102">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d8cc2-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="d8cc2-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8cc2-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8cc2-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d8cc2-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d8cc2-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8cc2-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d8cc2-106">Attributes</span></span>  
 <span data-ttu-id="d8cc2-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d8cc2-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d8cc2-108">Child Elements</span></span>  
  
|<span data-ttu-id="d8cc2-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8cc2-109">Element</span></span>|<span data-ttu-id="d8cc2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8cc2-110">Description</span></span>|  
|-------------|-----------------|  
|[\<state>](states.md)|<span data-ttu-id="d8cc2-111">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-111">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d8cc2-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d8cc2-112">Parent Elements</span></span>  
  
|<span data-ttu-id="d8cc2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="d8cc2-113">Element</span></span>|<span data-ttu-id="d8cc2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8cc2-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="d8cc2-115">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-115">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8cc2-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8cc2-116">Remarks</span></span>  
 <span data-ttu-id="d8cc2-117">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-117">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="d8cc2-118">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-118">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="d8cc2-119">State</span><span class="sxs-lookup"><span data-stu-id="d8cc2-119">State</span></span>|<span data-ttu-id="d8cc2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8cc2-120">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d8cc2-121">Anulado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-121">Aborted</span></span>|<span data-ttu-id="d8cc2-122">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-122">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="d8cc2-123">Completado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-123">Completed</span></span>|<span data-ttu-id="d8cc2-124">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-124">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="d8cc2-125">Deleted</span><span class="sxs-lookup"><span data-stu-id="d8cc2-125">Deleted</span></span>|<span data-ttu-id="d8cc2-126">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-126">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="d8cc2-127">Inactivo</span><span class="sxs-lookup"><span data-stu-id="d8cc2-127">Idle</span></span>|<span data-ttu-id="d8cc2-128">La instancia del flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-128">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="d8cc2-129">Guardado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-129">Persisted</span></span>|<span data-ttu-id="d8cc2-130">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-130">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="d8cc2-131">Reanudado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-131">Resumed</span></span>|<span data-ttu-id="d8cc2-132">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-132">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="d8cc2-133">Comenzado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-133">Started</span></span>|<span data-ttu-id="d8cc2-134">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-134">The workflow instance is started.</span></span>|  
|<span data-ttu-id="d8cc2-135">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="d8cc2-135">UnhandledException</span></span>|<span data-ttu-id="d8cc2-136">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-136">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="d8cc2-137">Descargado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-137">Unloaded</span></span>|<span data-ttu-id="d8cc2-138">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-138">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="d8cc2-139">Canceled</span><span class="sxs-lookup"><span data-stu-id="d8cc2-139">Canceled</span></span>|<span data-ttu-id="d8cc2-140">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-140">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="d8cc2-141">Suspended</span><span class="sxs-lookup"><span data-stu-id="d8cc2-141">Suspended</span></span>|<span data-ttu-id="d8cc2-142">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-142">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="d8cc2-143">Finalizado</span><span class="sxs-lookup"><span data-stu-id="d8cc2-143">Terminated</span></span>|<span data-ttu-id="d8cc2-144">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-144">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="d8cc2-145">No suspendido</span><span class="sxs-lookup"><span data-stu-id="d8cc2-145">Unsuspended</span></span>|<span data-ttu-id="d8cc2-146">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-146">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d8cc2-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8cc2-147">Example</span></span>  
 <span data-ttu-id="d8cc2-148">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="d8cc2-148">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8cc2-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8cc2-149">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d8cc2-150">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d8cc2-150">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d8cc2-151">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d8cc2-151">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
