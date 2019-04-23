---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: e54f98c980f60d02377e38d53d9d0eb48581eec0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132488"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="cff50-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="cff50-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="cff50-102">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="cff50-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="cff50-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cff50-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cff50-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cff50-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cff50-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="cff50-105">\<tracking></span></span>  
<span data-ttu-id="cff50-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cff50-106">\<trackingProfile></span></span>  
<span data-ttu-id="cff50-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="cff50-107">\<workflow></span></span>  
<span data-ttu-id="cff50-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="cff50-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff50-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cff50-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cff50-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cff50-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cff50-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cff50-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cff50-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cff50-112">Attributes</span></span>  
 <span data-ttu-id="cff50-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cff50-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cff50-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cff50-114">Child Elements</span></span>  
  
|<span data-ttu-id="cff50-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cff50-115">Element</span></span>|<span data-ttu-id="cff50-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff50-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cff50-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="cff50-117">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="cff50-118">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cff50-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cff50-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cff50-119">Parent Elements</span></span>  
  
|<span data-ttu-id="cff50-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="cff50-120">Element</span></span>|<span data-ttu-id="cff50-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="cff50-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cff50-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cff50-122">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cff50-123">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="cff50-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cff50-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cff50-124">Remarks</span></span>  
 <span data-ttu-id="cff50-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="cff50-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="cff50-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cff50-126">Example</span></span>  
 <span data-ttu-id="cff50-127">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="cff50-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cff50-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="cff50-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cff50-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cff50-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cff50-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cff50-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
