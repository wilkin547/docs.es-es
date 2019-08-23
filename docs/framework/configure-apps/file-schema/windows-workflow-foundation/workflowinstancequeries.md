---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 0a32e6ee22cdf984e64c1b8fa16836c4c56d0380
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932741"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="b737c-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b737c-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="b737c-102">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="b737c-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="b737c-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b737c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b737c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b737c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b737c-105">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b737c-105">\<tracking></span></span>  
<span data-ttu-id="b737c-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b737c-106">\<trackingProfile></span></span>  
<span data-ttu-id="b737c-107">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b737c-107">\<workflow></span></span>  
<span data-ttu-id="b737c-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="b737c-108">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b737c-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b737c-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b737c-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b737c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b737c-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b737c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b737c-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b737c-112">Attributes</span></span>  
 <span data-ttu-id="b737c-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b737c-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b737c-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b737c-114">Child Elements</span></span>  
  
|<span data-ttu-id="b737c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="b737c-115">Element</span></span>|<span data-ttu-id="b737c-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b737c-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b737c-117">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b737c-117">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="b737c-118">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b737c-118">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b737c-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b737c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b737c-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b737c-120">Element</span></span>|<span data-ttu-id="b737c-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b737c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b737c-122">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b737c-122">\<workflow></span></span>](workflow.md)|<span data-ttu-id="b737c-123">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="b737c-123">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b737c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b737c-124">Remarks</span></span>  
 <span data-ttu-id="b737c-125"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="b737c-125">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="b737c-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b737c-126">Example</span></span>  
 <span data-ttu-id="b737c-127">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="b737c-127">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b737c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b737c-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b737c-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b737c-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b737c-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b737c-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
