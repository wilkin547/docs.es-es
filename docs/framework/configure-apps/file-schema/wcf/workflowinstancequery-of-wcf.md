---
title: <workflowInstanceQuery> de WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: 726d4db3bad9f57663790e2bb4e081faba28f1ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278777"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="47d4e-102">\<workflowInstanceQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="47d4e-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="47d4e-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="47d4e-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="47d4e-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="47d4e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="47d4e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="47d4e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="47d4e-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="47d4e-106">\<tracking></span></span>  
<span data-ttu-id="47d4e-107">\<profiles></span><span class="sxs-lookup"><span data-stu-id="47d4e-107">\<profiles></span></span>  
<span data-ttu-id="47d4e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="47d4e-108">\<trackingProfile></span></span>  
<span data-ttu-id="47d4e-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="47d4e-109">\<workflow></span></span>  
<span data-ttu-id="47d4e-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="47d4e-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="47d4e-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="47d4e-111">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47d4e-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47d4e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47d4e-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="47d4e-113">Attributes and elements</span></span>  

<span data-ttu-id="47d4e-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="47d4e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47d4e-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="47d4e-115">Attributes</span></span>  

<span data-ttu-id="47d4e-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="47d4e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="47d4e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="47d4e-117">Child elements</span></span>  
  
|<span data-ttu-id="47d4e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="47d4e-118">Element</span></span>|<span data-ttu-id="47d4e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="47d4e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47d4e-120">\<states></span><span class="sxs-lookup"><span data-stu-id="47d4e-120">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="47d4e-121">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="47d4e-121">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47d4e-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="47d4e-122">Parent elements</span></span>  
  
|<span data-ttu-id="47d4e-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="47d4e-123">Element</span></span>|<span data-ttu-id="47d4e-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="47d4e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47d4e-125">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="47d4e-125">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="47d4e-126">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="47d4e-126">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47d4e-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47d4e-127">Remarks</span></span>  

<span data-ttu-id="47d4e-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="47d4e-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="47d4e-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47d4e-129">Example</span></span>  

<span data-ttu-id="47d4e-130">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="47d4e-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="47d4e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="47d4e-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="47d4e-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="47d4e-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="47d4e-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="47d4e-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
