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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 182a4082de6f1c67b7a0bc26662e2491623b2bba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="f7fbd-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="f7fbd-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="f7fbd-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="f7fbd-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f7fbd-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f7fbd-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f7fbd-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-106">\<tracking></span></span>  
<span data-ttu-id="f7fbd-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-107">\<trackingProfile></span></span>  
<span data-ttu-id="f7fbd-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-108">\<workflow></span></span>  
<span data-ttu-id="f7fbd-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7fbd-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7fbd-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7fbd-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7fbd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f7fbd-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7fbd-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7fbd-113">Attributes</span></span>  
 <span data-ttu-id="f7fbd-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7fbd-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7fbd-115">Child Elements</span></span>  
  
|<span data-ttu-id="f7fbd-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7fbd-116">Element</span></span>|<span data-ttu-id="f7fbd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7fbd-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7fbd-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="f7fbd-119">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f7fbd-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7fbd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f7fbd-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7fbd-121">Element</span></span>|<span data-ttu-id="f7fbd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7fbd-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7fbd-123">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f7fbd-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f7fbd-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7fbd-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7fbd-125">Remarks</span></span>  
 <span data-ttu-id="f7fbd-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="f7fbd-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="f7fbd-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7fbd-127">Example</span></span>  
 <span data-ttu-id="f7fbd-128">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="f7fbd-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7fbd-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7fbd-129">See Also</span></span>  
 <span data-ttu-id="f7fbd-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f7fbd-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="f7fbd-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="f7fbd-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="f7fbd-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f7fbd-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f7fbd-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f7fbd-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
