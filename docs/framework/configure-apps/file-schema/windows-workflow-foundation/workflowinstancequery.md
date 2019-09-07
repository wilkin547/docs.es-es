---
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 68e44584858e55c136bc3c3dc5f1fb333485fa17
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397510"
---
# <a name="workflowinstancequery"></a><span data-ttu-id="3c6cc-101">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="3c6cc-101">\<workflowInstanceQuery></span></span>
<span data-ttu-id="3c6cc-102">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="3c6cc-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="3c6cc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3c6cc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3c6cc-105">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3c6cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="3c6cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="3c6cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="3c6cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="3c6cc-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="3c6cc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQuery**</span><span class="sxs-lookup"><span data-stu-id="3c6cc-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c6cc-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c6cc-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c6cc-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c6cc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c6cc-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c6cc-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c6cc-114">Attributes</span></span>  
 <span data-ttu-id="3c6cc-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c6cc-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c6cc-116">Child Elements</span></span>  
  
|<span data-ttu-id="3c6cc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c6cc-117">Element</span></span>|<span data-ttu-id="3c6cc-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3c6cc-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c6cc-119">\<states></span><span class="sxs-lookup"><span data-stu-id="3c6cc-119">\<states></span></span>](states.md)|<span data-ttu-id="3c6cc-120">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c6cc-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c6cc-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3c6cc-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c6cc-122">Element</span></span>|<span data-ttu-id="3c6cc-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3c6cc-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c6cc-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="3c6cc-124">\<workflowInstanceQueries></span></span>](workflowinstancequeries.md)|<span data-ttu-id="3c6cc-125">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c6cc-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c6cc-126">Remarks</span></span>  
 <span data-ttu-id="3c6cc-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="3c6cc-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="3c6cc-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c6cc-128">Example</span></span>  
 <span data-ttu-id="3c6cc-129">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="3c6cc-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c6cc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c6cc-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3c6cc-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3c6cc-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c6cc-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3c6cc-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
