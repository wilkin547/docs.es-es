---
title: '&lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a7d9d19c4ea5ecd5dc7a7329eb3fdad657567864
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="b13fe-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="b13fe-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="b13fe-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="b13fe-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="b13fe-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b13fe-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b13fe-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b13fe-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b13fe-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="b13fe-106">\<tracking></span></span>  
<span data-ttu-id="b13fe-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b13fe-107">\<trackingProfile></span></span>  
<span data-ttu-id="b13fe-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b13fe-108">\<workflow></span></span>  
<span data-ttu-id="b13fe-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="b13fe-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="b13fe-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="b13fe-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13fe-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b13fe-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b13fe-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b13fe-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b13fe-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b13fe-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b13fe-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="b13fe-114">Attributes</span></span>  
 <span data-ttu-id="b13fe-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b13fe-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b13fe-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b13fe-116">Child Elements</span></span>  
  
|<span data-ttu-id="b13fe-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b13fe-117">Element</span></span>|<span data-ttu-id="b13fe-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b13fe-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b13fe-119">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="b13fe-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="b13fe-120">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b13fe-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b13fe-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b13fe-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b13fe-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="b13fe-122">Element</span></span>|<span data-ttu-id="b13fe-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="b13fe-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b13fe-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="b13fe-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="b13fe-125">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="b13fe-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b13fe-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b13fe-126">Remarks</span></span>  
 <span data-ttu-id="b13fe-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="b13fe-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b13fe-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b13fe-128">Example</span></span>  
 <span data-ttu-id="b13fe-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="b13fe-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b13fe-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b13fe-130">See Also</span></span>  
 <span data-ttu-id="b13fe-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b13fe-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b13fe-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b13fe-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b13fe-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b13fe-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b13fe-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b13fe-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
