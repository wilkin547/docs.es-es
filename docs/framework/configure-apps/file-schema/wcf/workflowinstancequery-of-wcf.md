---
title: '&lt;workflowInstanceQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 01867171941db82260d28b0825bdf3453e46e66c
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148180"
---
# <a name="ltworkflowinstancequerygt-of-wcf"></a><span data-ttu-id="02cb7-102">&lt;workflowInstanceQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="02cb7-102">&lt;workflowInstanceQuery&gt; of WCF</span></span>

<span data-ttu-id="02cb7-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="02cb7-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="02cb7-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="02cb7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="02cb7-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="02cb7-105">\<system.serviceModel></span></span>  
<span data-ttu-id="02cb7-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="02cb7-106">\<tracking></span></span>  
<span data-ttu-id="02cb7-107">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="02cb7-107">\<profiles></span></span>  
<span data-ttu-id="02cb7-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="02cb7-108">\<trackingProfile></span></span>  
<span data-ttu-id="02cb7-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="02cb7-109">\<workflow></span></span>  
<span data-ttu-id="02cb7-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="02cb7-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="02cb7-111">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="02cb7-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02cb7-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02cb7-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02cb7-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="02cb7-113">Attributes and elements</span></span>  

<span data-ttu-id="02cb7-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="02cb7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02cb7-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="02cb7-115">Attributes</span></span>  

<span data-ttu-id="02cb7-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="02cb7-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02cb7-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="02cb7-117">Child elements</span></span>  
  
|<span data-ttu-id="02cb7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="02cb7-118">Element</span></span>|<span data-ttu-id="02cb7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="02cb7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02cb7-120">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="02cb7-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="02cb7-121">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="02cb7-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02cb7-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="02cb7-122">Parent elements</span></span>  
  
|<span data-ttu-id="02cb7-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="02cb7-123">Element</span></span>|<span data-ttu-id="02cb7-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="02cb7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02cb7-125">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="02cb7-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="02cb7-126">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="02cb7-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02cb7-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02cb7-127">Remarks</span></span>  

<span data-ttu-id="02cb7-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="02cb7-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="02cb7-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="02cb7-129">Example</span></span>  

<span data-ttu-id="02cb7-130">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="02cb7-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="02cb7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="02cb7-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="02cb7-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="02cb7-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="02cb7-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="02cb7-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
