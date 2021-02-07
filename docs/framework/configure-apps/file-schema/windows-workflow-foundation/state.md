---
description: 'Más información acerca de: <state>'
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: c04ba8a791d08e65337ffc28cd86f5a4a6af150f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729763"
---
# \<state>

<span data-ttu-id="81e15-102">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="81e15-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="81e15-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="81e15-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="81e15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81e15-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81e15-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="81e15-105">Attributes and Elements</span></span>  

 <span data-ttu-id="81e15-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="81e15-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81e15-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="81e15-107">Attributes</span></span>  
  
|<span data-ttu-id="81e15-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="81e15-108">Attribute</span></span>|<span data-ttu-id="81e15-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="81e15-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81e15-110">name</span><span class="sxs-lookup"><span data-stu-id="81e15-110">name</span></span>|<span data-ttu-id="81e15-111">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="81e15-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81e15-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="81e15-112">Child Elements</span></span>  

 <span data-ttu-id="81e15-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="81e15-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81e15-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="81e15-114">Parent Elements</span></span>  
  
|<span data-ttu-id="81e15-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="81e15-115">Element</span></span>|<span data-ttu-id="81e15-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="81e15-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="81e15-117">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="81e15-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81e15-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="81e15-118">Remarks</span></span>  

 <span data-ttu-id="81e15-119">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="81e15-119">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="81e15-120">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="81e15-120">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="81e15-121">Estado</span><span class="sxs-lookup"><span data-stu-id="81e15-121">State</span></span>|<span data-ttu-id="81e15-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="81e15-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="81e15-123">Anulado</span><span class="sxs-lookup"><span data-stu-id="81e15-123">Aborted</span></span>|<span data-ttu-id="81e15-124">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="81e15-125">Completado</span><span class="sxs-lookup"><span data-stu-id="81e15-125">Completed</span></span>|<span data-ttu-id="81e15-126">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="81e15-127">Deleted</span><span class="sxs-lookup"><span data-stu-id="81e15-127">Deleted</span></span>|<span data-ttu-id="81e15-128">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="81e15-129">Inactivo</span><span class="sxs-lookup"><span data-stu-id="81e15-129">Idle</span></span>|<span data-ttu-id="81e15-130">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="81e15-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="81e15-131">Guardado</span><span class="sxs-lookup"><span data-stu-id="81e15-131">Persisted</span></span>|<span data-ttu-id="81e15-132">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="81e15-133">Reanudado</span><span class="sxs-lookup"><span data-stu-id="81e15-133">Resumed</span></span>|<span data-ttu-id="81e15-134">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="81e15-135">Iniciado</span><span class="sxs-lookup"><span data-stu-id="81e15-135">Started</span></span>|<span data-ttu-id="81e15-136">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="81e15-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="81e15-137">UnhandledException</span></span>|<span data-ttu-id="81e15-138">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="81e15-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="81e15-139">Descargado</span><span class="sxs-lookup"><span data-stu-id="81e15-139">Unloaded</span></span>|<span data-ttu-id="81e15-140">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="81e15-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="81e15-141">Canceled</span></span>|<span data-ttu-id="81e15-142">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="81e15-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="81e15-143">Suspended</span></span>|<span data-ttu-id="81e15-144">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="81e15-145">Finalizado</span><span class="sxs-lookup"><span data-stu-id="81e15-145">Terminated</span></span>|<span data-ttu-id="81e15-146">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="81e15-147">No suspendido</span><span class="sxs-lookup"><span data-stu-id="81e15-147">Unsuspended</span></span>|<span data-ttu-id="81e15-148">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e15-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="81e15-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81e15-149">Example</span></span>  

 <span data-ttu-id="81e15-150">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="81e15-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="81e15-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="81e15-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="81e15-152">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="81e15-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81e15-153">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="81e15-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
