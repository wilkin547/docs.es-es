---
title: <workflowInstanceQueries>de WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854775"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="c7324-102">\<workflowInstanceQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="c7324-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="c7324-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="c7324-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="c7324-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c7324-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c7324-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7324-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7324-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c7324-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c7324-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c7324-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="c7324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="c7324-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="c7324-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c7324-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="c7324-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c7324-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="c7324-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQueries**</span><span class="sxs-lookup"><span data-stu-id="c7324-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7324-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c7324-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7324-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c7324-113">Attributes and elements</span></span>

<span data-ttu-id="c7324-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c7324-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7324-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="c7324-115">Attributes</span></span>  

<span data-ttu-id="c7324-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c7324-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c7324-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c7324-117">Child elements</span></span>  
  
|<span data-ttu-id="c7324-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7324-118">Element</span></span>|<span data-ttu-id="c7324-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c7324-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7324-120">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c7324-120">\<workflowInstanceQuery></span></span>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="c7324-121">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c7324-121">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7324-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c7324-122">Parent elements</span></span>  
  
|<span data-ttu-id="c7324-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="c7324-123">Element</span></span>|<span data-ttu-id="c7324-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c7324-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7324-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c7324-125">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="c7324-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="c7324-126">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7324-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c7324-127">Remarks</span></span>

<span data-ttu-id="c7324-128"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="c7324-128">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="c7324-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7324-129">Example</span></span>  

<span data-ttu-id="c7324-130">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="c7324-130">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="c7324-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7324-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c7324-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c7324-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c7324-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c7324-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
