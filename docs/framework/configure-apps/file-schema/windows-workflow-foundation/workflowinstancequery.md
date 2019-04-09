---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 6fe02cfea91633da41c8ebc7d8a78dd005ad3f4a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080909"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="90346-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="90346-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="90346-102">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="90346-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="90346-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="90346-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="90346-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="90346-104">\<system.serviceModel></span></span>  
<span data-ttu-id="90346-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="90346-105">\<tracking></span></span>  
<span data-ttu-id="90346-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="90346-106">\<trackingProfile></span></span>  
<span data-ttu-id="90346-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="90346-107">\<workflow></span></span>  
<span data-ttu-id="90346-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="90346-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="90346-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="90346-109">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90346-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90346-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90346-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="90346-111">Attributes and Elements</span></span>  
 <span data-ttu-id="90346-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="90346-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90346-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="90346-113">Attributes</span></span>  
 <span data-ttu-id="90346-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="90346-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="90346-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="90346-115">Child Elements</span></span>  
  
|<span data-ttu-id="90346-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="90346-116">Element</span></span>|<span data-ttu-id="90346-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="90346-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90346-118">\<states></span><span class="sxs-lookup"><span data-stu-id="90346-118">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="90346-119">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="90346-119">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90346-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="90346-120">Parent Elements</span></span>  
  
|<span data-ttu-id="90346-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="90346-121">Element</span></span>|<span data-ttu-id="90346-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="90346-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90346-123">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="90346-123">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="90346-124">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="90346-124">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90346-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90346-125">Remarks</span></span>  
 <span data-ttu-id="90346-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="90346-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="90346-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="90346-127">Example</span></span>  
 <span data-ttu-id="90346-128">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="90346-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90346-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="90346-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="90346-130">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="90346-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="90346-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="90346-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
