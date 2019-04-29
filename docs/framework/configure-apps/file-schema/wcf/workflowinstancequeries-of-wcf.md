---
title: <workflowInstanceQueries> de WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 89e122b87743a81a80ce63b382ae235c1c4863bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790525"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="5d70b-102">\<workflowInstanceQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="5d70b-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="5d70b-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="5d70b-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="5d70b-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5d70b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5d70b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5d70b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5d70b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5d70b-106">\<tracking></span></span>  
<span data-ttu-id="5d70b-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="5d70b-107">\<profiles></span></span>  
<span data-ttu-id="5d70b-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5d70b-108">\<trackingProfile></span></span>  
<span data-ttu-id="5d70b-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="5d70b-109">\<workflow></span></span>  
<span data-ttu-id="5d70b-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="5d70b-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d70b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d70b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d70b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d70b-112">Attributes and elements</span></span>

<span data-ttu-id="5d70b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d70b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d70b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d70b-114">Attributes</span></span>  

<span data-ttu-id="5d70b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5d70b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d70b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d70b-116">Child elements</span></span>  
  
|<span data-ttu-id="5d70b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d70b-117">Element</span></span>|<span data-ttu-id="5d70b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d70b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d70b-119">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="5d70b-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="5d70b-120">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d70b-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d70b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d70b-121">Parent elements</span></span>  
  
|<span data-ttu-id="5d70b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d70b-122">Element</span></span>|<span data-ttu-id="5d70b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d70b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d70b-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5d70b-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5d70b-125">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) propiedad.</span><span class="sxs-lookup"><span data-stu-id="5d70b-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d70b-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d70b-126">Remarks</span></span>

<span data-ttu-id="5d70b-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="5d70b-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="5d70b-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d70b-128">Example</span></span>  

<span data-ttu-id="5d70b-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="5d70b-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="5d70b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d70b-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5d70b-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d70b-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5d70b-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5d70b-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
