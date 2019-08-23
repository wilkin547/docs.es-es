---
title: <workflowInstanceQueries>de WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: feae65a75f9f0b2b1b398f3f9e80ac4c8d971dcc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915301"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="983ae-102">\<workflowInstanceQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="983ae-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="983ae-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="983ae-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="983ae-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="983ae-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="983ae-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="983ae-105">\<system.serviceModel></span></span>  
<span data-ttu-id="983ae-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="983ae-106">\<tracking></span></span>  
<span data-ttu-id="983ae-107">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="983ae-107">\<profiles></span></span>  
<span data-ttu-id="983ae-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="983ae-108">\<trackingProfile></span></span>  
<span data-ttu-id="983ae-109">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="983ae-109">\<workflow></span></span>  
<span data-ttu-id="983ae-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="983ae-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983ae-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="983ae-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="983ae-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="983ae-112">Attributes and elements</span></span>

<span data-ttu-id="983ae-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="983ae-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="983ae-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="983ae-114">Attributes</span></span>  

<span data-ttu-id="983ae-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="983ae-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="983ae-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="983ae-116">Child elements</span></span>  
  
|<span data-ttu-id="983ae-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="983ae-117">Element</span></span>|<span data-ttu-id="983ae-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="983ae-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="983ae-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="983ae-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="983ae-120">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="983ae-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="983ae-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="983ae-121">Parent elements</span></span>  
  
|<span data-ttu-id="983ae-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="983ae-122">Element</span></span>|<span data-ttu-id="983ae-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="983ae-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="983ae-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="983ae-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="983ae-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="983ae-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="983ae-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="983ae-126">Remarks</span></span>

<span data-ttu-id="983ae-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="983ae-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="983ae-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="983ae-128">Example</span></span>  

<span data-ttu-id="983ae-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="983ae-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="983ae-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="983ae-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="983ae-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="983ae-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="983ae-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="983ae-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
