---
title: <state>de WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854952"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="8a861-102">\<state>de WCF,\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="8a861-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="8a861-103">Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8a861-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="8a861-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="8a861-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="8a861-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a861-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a861-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8a861-106">Attributes and elements</span></span>

<span data-ttu-id="8a861-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8a861-107">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="8a861-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="8a861-108">Attributes</span></span>

|<span data-ttu-id="8a861-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="8a861-109">Attribute</span></span>|<span data-ttu-id="8a861-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a861-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="8a861-111">Una cadena que especifica un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8a861-111">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a861-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8a861-112">Child elements</span></span>

<span data-ttu-id="8a861-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8a861-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="8a861-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8a861-114">Parent elements</span></span>

|<span data-ttu-id="8a861-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="8a861-115">Element</span></span>|<span data-ttu-id="8a861-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a861-116">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="8a861-117">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8a861-117">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a861-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a861-118">Remarks</span></span>  

<span data-ttu-id="8a861-119">Los registros devueltos se filtran por los estados de esta colección.</span><span class="sxs-lookup"><span data-stu-id="8a861-119">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="8a861-120">Los valores de estado posibles se describen en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="8a861-120">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="8a861-121">State</span><span class="sxs-lookup"><span data-stu-id="8a861-121">State</span></span>|<span data-ttu-id="8a861-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a861-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8a861-123">Anulado</span><span class="sxs-lookup"><span data-stu-id="8a861-123">Aborted</span></span>|<span data-ttu-id="8a861-124">Se ha anulado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-124">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="8a861-125">Completado</span><span class="sxs-lookup"><span data-stu-id="8a861-125">Completed</span></span>|<span data-ttu-id="8a861-126">Se ha completado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-126">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="8a861-127">Deleted</span><span class="sxs-lookup"><span data-stu-id="8a861-127">Deleted</span></span>|<span data-ttu-id="8a861-128">Se ha eliminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-128">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="8a861-129">Inactivo</span><span class="sxs-lookup"><span data-stu-id="8a861-129">Idle</span></span>|<span data-ttu-id="8a861-130">La instancia del flujo de trabajo está inactiva.</span><span class="sxs-lookup"><span data-stu-id="8a861-130">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="8a861-131">Guardado</span><span class="sxs-lookup"><span data-stu-id="8a861-131">Persisted</span></span>|<span data-ttu-id="8a861-132">Se ha guardado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-132">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="8a861-133">Reanudado</span><span class="sxs-lookup"><span data-stu-id="8a861-133">Resumed</span></span>|<span data-ttu-id="8a861-134">Se ha reanudado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-134">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="8a861-135">Comenzado</span><span class="sxs-lookup"><span data-stu-id="8a861-135">Started</span></span>|<span data-ttu-id="8a861-136">Se ha iniciado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-136">The workflow instance is started.</span></span>|  
|<span data-ttu-id="8a861-137">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="8a861-137">UnhandledException</span></span>|<span data-ttu-id="8a861-138">La instancia de flujo de trabajo ha detectado una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="8a861-138">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="8a861-139">Descargado</span><span class="sxs-lookup"><span data-stu-id="8a861-139">Unloaded</span></span>|<span data-ttu-id="8a861-140">Se ha descargado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-140">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="8a861-141">Canceled</span><span class="sxs-lookup"><span data-stu-id="8a861-141">Canceled</span></span>|<span data-ttu-id="8a861-142">Se ha cancelado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-142">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="8a861-143">Suspended</span><span class="sxs-lookup"><span data-stu-id="8a861-143">Suspended</span></span>|<span data-ttu-id="8a861-144">Se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-144">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="8a861-145">Finalizado</span><span class="sxs-lookup"><span data-stu-id="8a861-145">Terminated</span></span>|<span data-ttu-id="8a861-146">Se ha terminado la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-146">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="8a861-147">No suspendido</span><span class="sxs-lookup"><span data-stu-id="8a861-147">Unsuspended</span></span>|<span data-ttu-id="8a861-148">No se suspende la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8a861-148">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a861-149">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a861-149">Example</span></span>

<span data-ttu-id="8a861-150">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="8a861-150">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="8a861-151">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8a861-151">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8a861-152">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="8a861-152">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8a861-153">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8a861-153">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
