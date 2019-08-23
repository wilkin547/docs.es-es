---
title: <workflowInstanceQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 7e15d7654aeafa5fa7b87922283d6520d5493242
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915222"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="04728-102">\<workflowInstanceQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="04728-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="04728-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="04728-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="04728-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="04728-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="04728-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="04728-105">\<system.serviceModel></span></span>  
<span data-ttu-id="04728-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="04728-106">\<tracking></span></span>  
<span data-ttu-id="04728-107">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="04728-107">\<profiles></span></span>  
<span data-ttu-id="04728-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="04728-108">\<trackingProfile></span></span>  
<span data-ttu-id="04728-109">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="04728-109">\<workflow></span></span>  
<span data-ttu-id="04728-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="04728-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="04728-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="04728-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04728-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04728-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="04728-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="04728-113">Attributes and elements</span></span>  

<span data-ttu-id="04728-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="04728-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="04728-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="04728-115">Attributes</span></span>  

<span data-ttu-id="04728-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="04728-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="04728-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="04728-117">Child elements</span></span>  
  
|<span data-ttu-id="04728-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="04728-118">Element</span></span>|<span data-ttu-id="04728-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="04728-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04728-120">\<states></span><span class="sxs-lookup"><span data-stu-id="04728-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="04728-121">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="04728-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="04728-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="04728-122">Parent elements</span></span>  
  
|<span data-ttu-id="04728-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="04728-123">Element</span></span>|<span data-ttu-id="04728-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="04728-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="04728-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="04728-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="04728-126">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="04728-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04728-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04728-127">Remarks</span></span>  

<span data-ttu-id="04728-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="04728-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="04728-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04728-129">Example</span></span>  

<span data-ttu-id="04728-130">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="04728-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="04728-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="04728-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="04728-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="04728-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="04728-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="04728-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
