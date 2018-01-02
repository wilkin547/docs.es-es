---
title: '&lt;workflowInstanceQuery&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63b56a927c16a746352e030df2a4de2ed28f7a09
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="43655-102">&lt;workflowInstanceQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="43655-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>
<span data-ttu-id="43655-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="43655-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="43655-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="43655-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="43655-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="43655-105">\<system.serviceModel></span></span>  
<span data-ttu-id="43655-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="43655-106">\<tracking></span></span>  
<span data-ttu-id="43655-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="43655-107">\<trackingProfile></span></span>  
<span data-ttu-id="43655-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="43655-108">\<workflow></span></span>  
<span data-ttu-id="43655-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="43655-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="43655-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="43655-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43655-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43655-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43655-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43655-112">Attributes and Elements</span></span>  
 <span data-ttu-id="43655-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43655-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43655-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="43655-114">Attributes</span></span>  
 <span data-ttu-id="43655-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43655-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43655-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43655-116">Child Elements</span></span>  
  
|<span data-ttu-id="43655-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="43655-117">Element</span></span>|<span data-ttu-id="43655-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="43655-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43655-119">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="43655-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="43655-120">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="43655-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43655-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43655-121">Parent Elements</span></span>  
  
|<span data-ttu-id="43655-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="43655-122">Element</span></span>|<span data-ttu-id="43655-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="43655-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43655-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="43655-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="43655-125">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="43655-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43655-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43655-126">Remarks</span></span>  
 <span data-ttu-id="43655-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="43655-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="43655-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="43655-128">Example</span></span>  
 <span data-ttu-id="43655-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="43655-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43655-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="43655-130">See Also</span></span>  
 <span data-ttu-id="43655-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="43655-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="43655-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="43655-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="43655-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="43655-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="43655-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="43655-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
