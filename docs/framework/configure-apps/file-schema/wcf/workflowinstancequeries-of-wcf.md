---
title: '&lt;workflowInstanceQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 300637031c64f7c9e072f04835fc3590348ddc9e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50192699"
---
# <a name="ltworkflowinstancequeriesgt-of-wcf"></a><span data-ttu-id="bfeeb-102">&lt;workflowInstanceQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="bfeeb-102">&lt;workflowInstanceQueries&gt; of WCF</span></span>

<span data-ttu-id="bfeeb-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="bfeeb-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bfeeb-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bfeeb-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bfeeb-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bfeeb-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-106">\<tracking></span></span>  
<span data-ttu-id="bfeeb-107">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-107">\<profiles></span></span>  
<span data-ttu-id="bfeeb-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-108">\<trackingProfile></span></span>  
<span data-ttu-id="bfeeb-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-109">\<workflow></span></span>  
<span data-ttu-id="bfeeb-110">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-110">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfeeb-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bfeeb-111">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfeeb-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bfeeb-112">Attributes and elements</span></span>

<span data-ttu-id="bfeeb-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfeeb-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="bfeeb-114">Attributes</span></span>  

<span data-ttu-id="bfeeb-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bfeeb-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bfeeb-116">Child elements</span></span>  
  
|<span data-ttu-id="bfeeb-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfeeb-117">Element</span></span>|<span data-ttu-id="bfeeb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfeeb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfeeb-119">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-119">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="bfeeb-120">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-120">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bfeeb-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bfeeb-121">Parent elements</span></span>  
  
|<span data-ttu-id="bfeeb-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="bfeeb-122">Element</span></span>|<span data-ttu-id="bfeeb-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="bfeeb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfeeb-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="bfeeb-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="bfeeb-125">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) propiedad.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-125">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](https://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfeeb-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bfeeb-126">Remarks</span></span>

<span data-ttu-id="bfeeb-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="bfeeb-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="bfeeb-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfeeb-128">Example</span></span>  

<span data-ttu-id="bfeeb-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="bfeeb-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>  
    <states>  
      <state name="Started"/>  
    </states>  
  </workflowInstanceQuery>  
</workflowInstanceQueries>
```
  
## <a name="see-also"></a><span data-ttu-id="bfeeb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="bfeeb-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bfeeb-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="bfeeb-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bfeeb-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bfeeb-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
