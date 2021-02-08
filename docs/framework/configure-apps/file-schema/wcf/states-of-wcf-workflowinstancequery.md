---
description: 'Más información sobre: <states> de WCF, <workflowInstanceQuery>'
title: <states> de WCF, <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 66b3008b352d1f76c30aab9a0ec038836f33d408
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786647"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="a22e5-103">\<states> de WCF, \<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a22e5-103">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="a22e5-104">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a22e5-104">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="a22e5-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a22e5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**  
  
## <a name="syntax"></a><span data-ttu-id="a22e5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a22e5-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a22e5-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a22e5-107">Attributes and elements</span></span>

<span data-ttu-id="a22e5-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a22e5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a22e5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a22e5-109">Attributes</span></span>  

<span data-ttu-id="a22e5-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a22e5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a22e5-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a22e5-111">Child elements</span></span>
  
|<span data-ttu-id="a22e5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="a22e5-112">Element</span></span>|<span data-ttu-id="a22e5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="a22e5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="a22e5-114">Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a22e5-114">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a22e5-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a22e5-115">Parent elements</span></span>  
  
|<span data-ttu-id="a22e5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a22e5-116">Element</span></span>|<span data-ttu-id="a22e5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a22e5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="a22e5-118">Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="a22e5-118">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a22e5-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a22e5-119">Remarks</span></span>

<span data-ttu-id="a22e5-120">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="a22e5-120">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="a22e5-121">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="a22e5-121">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="a22e5-122">Estado</span><span class="sxs-lookup"><span data-stu-id="a22e5-122">State</span></span>|<span data-ttu-id="a22e5-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a22e5-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a22e5-124">Anulado</span><span class="sxs-lookup"><span data-stu-id="a22e5-124">Aborted</span></span>|<span data-ttu-id="a22e5-125">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-125">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="a22e5-126">Completado</span><span class="sxs-lookup"><span data-stu-id="a22e5-126">Completed</span></span>|<span data-ttu-id="a22e5-127">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-127">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="a22e5-128">Deleted</span><span class="sxs-lookup"><span data-stu-id="a22e5-128">Deleted</span></span>|<span data-ttu-id="a22e5-129">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-129">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="a22e5-130">Inactivo</span><span class="sxs-lookup"><span data-stu-id="a22e5-130">Idle</span></span>|<span data-ttu-id="a22e5-131">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="a22e5-131">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="a22e5-132">Guardado</span><span class="sxs-lookup"><span data-stu-id="a22e5-132">Persisted</span></span>|<span data-ttu-id="a22e5-133">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-133">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="a22e5-134">Reanudado</span><span class="sxs-lookup"><span data-stu-id="a22e5-134">Resumed</span></span>|<span data-ttu-id="a22e5-135">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-135">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="a22e5-136">Iniciado</span><span class="sxs-lookup"><span data-stu-id="a22e5-136">Started</span></span>|<span data-ttu-id="a22e5-137">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-137">The workflow instance is started.</span></span>|  
|<span data-ttu-id="a22e5-138">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="a22e5-138">UnhandledException</span></span>|<span data-ttu-id="a22e5-139">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="a22e5-139">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="a22e5-140">Descargado</span><span class="sxs-lookup"><span data-stu-id="a22e5-140">Unloaded</span></span>|<span data-ttu-id="a22e5-141">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-141">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="a22e5-142">Canceled</span><span class="sxs-lookup"><span data-stu-id="a22e5-142">Canceled</span></span>|<span data-ttu-id="a22e5-143">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-143">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="a22e5-144">Suspended</span><span class="sxs-lookup"><span data-stu-id="a22e5-144">Suspended</span></span>|<span data-ttu-id="a22e5-145">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-145">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="a22e5-146">Finalizado</span><span class="sxs-lookup"><span data-stu-id="a22e5-146">Terminated</span></span>|<span data-ttu-id="a22e5-147">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-147">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="a22e5-148">No suspendido</span><span class="sxs-lookup"><span data-stu-id="a22e5-148">Unsuspended</span></span>|<span data-ttu-id="a22e5-149">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a22e5-149">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a22e5-150">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a22e5-150">Example</span></span>

<span data-ttu-id="a22e5-151">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="a22e5-151">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="a22e5-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="a22e5-152">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a22e5-153">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a22e5-153">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a22e5-154">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a22e5-154">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
