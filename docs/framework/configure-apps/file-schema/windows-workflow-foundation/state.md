---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 169fa900b5be9a9577818b68b540184afd4a6681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169731"
---
# \<state>

<span data-ttu-id="af03e-101">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="af03e-101">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="af03e-102">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="af03e-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="af03e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af03e-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af03e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af03e-104">Attributes and Elements</span></span>  

 <span data-ttu-id="af03e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af03e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af03e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="af03e-106">Attributes</span></span>  
  
|<span data-ttu-id="af03e-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="af03e-107">Attribute</span></span>|<span data-ttu-id="af03e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="af03e-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af03e-109">name</span><span class="sxs-lookup"><span data-stu-id="af03e-109">name</span></span>|<span data-ttu-id="af03e-110">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="af03e-110">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af03e-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af03e-111">Child Elements</span></span>  

 <span data-ttu-id="af03e-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af03e-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af03e-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af03e-113">Parent Elements</span></span>  
  
|<span data-ttu-id="af03e-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="af03e-114">Element</span></span>|<span data-ttu-id="af03e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="af03e-115">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="af03e-116">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="af03e-116">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af03e-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="af03e-117">Remarks</span></span>  

 <span data-ttu-id="af03e-118">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="af03e-118">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="af03e-119">En la siguiente tabla se describen los valores de estado posibles.</span><span class="sxs-lookup"><span data-stu-id="af03e-119">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="af03e-120">Estado</span><span class="sxs-lookup"><span data-stu-id="af03e-120">State</span></span>|<span data-ttu-id="af03e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="af03e-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="af03e-122">Anulado</span><span class="sxs-lookup"><span data-stu-id="af03e-122">Aborted</span></span>|<span data-ttu-id="af03e-123">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-123">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="af03e-124">Completado</span><span class="sxs-lookup"><span data-stu-id="af03e-124">Completed</span></span>|<span data-ttu-id="af03e-125">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-125">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="af03e-126">Deleted</span><span class="sxs-lookup"><span data-stu-id="af03e-126">Deleted</span></span>|<span data-ttu-id="af03e-127">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-127">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="af03e-128">Inactivo</span><span class="sxs-lookup"><span data-stu-id="af03e-128">Idle</span></span>|<span data-ttu-id="af03e-129">La instancia de flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="af03e-129">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="af03e-130">Guardado</span><span class="sxs-lookup"><span data-stu-id="af03e-130">Persisted</span></span>|<span data-ttu-id="af03e-131">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-131">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="af03e-132">Reanudado</span><span class="sxs-lookup"><span data-stu-id="af03e-132">Resumed</span></span>|<span data-ttu-id="af03e-133">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-133">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="af03e-134">Iniciado</span><span class="sxs-lookup"><span data-stu-id="af03e-134">Started</span></span>|<span data-ttu-id="af03e-135">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-135">The workflow instance is started.</span></span>|  
|<span data-ttu-id="af03e-136">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="af03e-136">UnhandledException</span></span>|<span data-ttu-id="af03e-137">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="af03e-137">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="af03e-138">Descargado</span><span class="sxs-lookup"><span data-stu-id="af03e-138">Unloaded</span></span>|<span data-ttu-id="af03e-139">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-139">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="af03e-140">Canceled</span><span class="sxs-lookup"><span data-stu-id="af03e-140">Canceled</span></span>|<span data-ttu-id="af03e-141">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-141">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="af03e-142">Suspended</span><span class="sxs-lookup"><span data-stu-id="af03e-142">Suspended</span></span>|<span data-ttu-id="af03e-143">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-143">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="af03e-144">Finalizado</span><span class="sxs-lookup"><span data-stu-id="af03e-144">Terminated</span></span>|<span data-ttu-id="af03e-145">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-145">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="af03e-146">No suspendido</span><span class="sxs-lookup"><span data-stu-id="af03e-146">Unsuspended</span></span>|<span data-ttu-id="af03e-147">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="af03e-147">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="af03e-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af03e-148">Example</span></span>  

 <span data-ttu-id="af03e-149">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="af03e-149">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af03e-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="af03e-150">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="af03e-151">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="af03e-151">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="af03e-152">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="af03e-152">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
