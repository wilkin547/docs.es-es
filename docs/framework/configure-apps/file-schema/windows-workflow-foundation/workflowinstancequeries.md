---
title: '&lt;workflowInstanceQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a65f6b888e210c1786395bbbb9f60050fe8e2c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="83774-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="83774-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="83774-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="83774-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="83774-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="83774-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="83774-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="83774-105">\<system.serviceModel></span></span>  
<span data-ttu-id="83774-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="83774-106">\<tracking></span></span>  
<span data-ttu-id="83774-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="83774-107">\<trackingProfile></span></span>  
<span data-ttu-id="83774-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="83774-108">\<workflow></span></span>  
<span data-ttu-id="83774-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="83774-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83774-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83774-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83774-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83774-111">Attributes and Elements</span></span>  
 <span data-ttu-id="83774-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83774-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83774-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="83774-113">Attributes</span></span>  
 <span data-ttu-id="83774-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83774-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="83774-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83774-115">Child Elements</span></span>  
  
|<span data-ttu-id="83774-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="83774-116">Element</span></span>|<span data-ttu-id="83774-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="83774-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83774-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="83774-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="83774-119">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="83774-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83774-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83774-120">Parent Elements</span></span>  
  
|<span data-ttu-id="83774-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="83774-121">Element</span></span>|<span data-ttu-id="83774-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="83774-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83774-123">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="83774-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="83774-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="83774-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83774-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83774-125">Remarks</span></span>  
 <span data-ttu-id="83774-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="83774-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="83774-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83774-127">Example</span></span>  
 <span data-ttu-id="83774-128">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="83774-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83774-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="83774-129">See Also</span></span>  
 <span data-ttu-id="83774-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="83774-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="83774-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="83774-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="83774-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="83774-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="83774-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="83774-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
