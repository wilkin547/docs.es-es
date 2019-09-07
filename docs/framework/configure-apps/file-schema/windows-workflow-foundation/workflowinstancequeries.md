---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 11e301de1ab3dbd4c97f236bfd07c5de4a632272
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398576"
---
# <a name="workflowinstancequeries"></a><span data-ttu-id="a6223-101">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a6223-101">\<workflowInstanceQueries></span></span>
<span data-ttu-id="a6223-102">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="a6223-102">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="a6223-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="a6223-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a6223-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a6223-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a6223-105">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a6223-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a6223-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="a6223-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="a6223-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="a6223-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="a6223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a6223-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="a6223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQueries**</span><span class="sxs-lookup"><span data-stu-id="a6223-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6223-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6223-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6223-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6223-111">Attributes and Elements</span></span>  

<span data-ttu-id="a6223-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6223-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6223-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6223-113">Attributes</span></span>  

<span data-ttu-id="a6223-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a6223-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6223-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6223-115">Child Elements</span></span>  
  
|<span data-ttu-id="a6223-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6223-116">Element</span></span>|<span data-ttu-id="a6223-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6223-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6223-118">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="a6223-118">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="a6223-119">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6223-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6223-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6223-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a6223-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6223-121">Element</span></span>|<span data-ttu-id="a6223-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a6223-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6223-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a6223-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="a6223-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="a6223-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6223-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6223-125">Remarks</span></span>  

<span data-ttu-id="a6223-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="a6223-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a6223-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a6223-127">Example</span></span>  

<span data-ttu-id="a6223-128">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="a6223-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a6223-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6223-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a6223-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a6223-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a6223-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a6223-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
