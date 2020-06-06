---
title: <states>de WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 5b779cf1074687dbd648b23d04f7cf3a354a2014
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855030"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="37c0a-102">\<states>de WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="37c0a-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="37c0a-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="37c0a-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="37c0a-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="37c0a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="37c0a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37c0a-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37c0a-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37c0a-106">Attributes and elements</span></span>

<span data-ttu-id="37c0a-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37c0a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37c0a-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="37c0a-108">Attributes</span></span>  

<span data-ttu-id="37c0a-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37c0a-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37c0a-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37c0a-110">Child elements</span></span>
  
|<span data-ttu-id="37c0a-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="37c0a-111">Element</span></span>|<span data-ttu-id="37c0a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="37c0a-112">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="37c0a-113">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="37c0a-113">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37c0a-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37c0a-114">Parent elements</span></span>  
  
|<span data-ttu-id="37c0a-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="37c0a-115">Element</span></span>|<span data-ttu-id="37c0a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="37c0a-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="37c0a-117">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="37c0a-117">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37c0a-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37c0a-118">Remarks</span></span>

<span data-ttu-id="37c0a-119">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="37c0a-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="37c0a-120">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="37c0a-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="37c0a-121">State</span><span class="sxs-lookup"><span data-stu-id="37c0a-121">State</span></span>|<span data-ttu-id="37c0a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="37c0a-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="37c0a-123">Anulado</span><span class="sxs-lookup"><span data-stu-id="37c0a-123">Aborted</span></span>|<span data-ttu-id="37c0a-124">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="37c0a-125">Completado</span><span class="sxs-lookup"><span data-stu-id="37c0a-125">Completed</span></span>|<span data-ttu-id="37c0a-126">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="37c0a-127">Deleted</span><span class="sxs-lookup"><span data-stu-id="37c0a-127">Deleted</span></span>|<span data-ttu-id="37c0a-128">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="37c0a-129">Inactivo</span><span class="sxs-lookup"><span data-stu-id="37c0a-129">Idle</span></span>|<span data-ttu-id="37c0a-130">La instancia del flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="37c0a-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="37c0a-131">Guardado</span><span class="sxs-lookup"><span data-stu-id="37c0a-131">Persisted</span></span>|<span data-ttu-id="37c0a-132">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="37c0a-133">Reanudado</span><span class="sxs-lookup"><span data-stu-id="37c0a-133">Resumed</span></span>|<span data-ttu-id="37c0a-134">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="37c0a-135">Comenzado</span><span class="sxs-lookup"><span data-stu-id="37c0a-135">Started</span></span>|<span data-ttu-id="37c0a-136">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="37c0a-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="37c0a-137">UnhandledException</span></span>|<span data-ttu-id="37c0a-138">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="37c0a-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="37c0a-139">Descargado</span><span class="sxs-lookup"><span data-stu-id="37c0a-139">Unloaded</span></span>|<span data-ttu-id="37c0a-140">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="37c0a-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="37c0a-141">Canceled</span></span>|<span data-ttu-id="37c0a-142">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="37c0a-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="37c0a-143">Suspended</span></span>|<span data-ttu-id="37c0a-144">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="37c0a-145">Finalizado</span><span class="sxs-lookup"><span data-stu-id="37c0a-145">Terminated</span></span>|<span data-ttu-id="37c0a-146">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="37c0a-147">No suspendido</span><span class="sxs-lookup"><span data-stu-id="37c0a-147">Unsuspended</span></span>|<span data-ttu-id="37c0a-148">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c0a-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="37c0a-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37c0a-149">Example</span></span>

<span data-ttu-id="37c0a-150">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="37c0a-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="37c0a-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37c0a-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="37c0a-152">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37c0a-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="37c0a-153">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="37c0a-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
