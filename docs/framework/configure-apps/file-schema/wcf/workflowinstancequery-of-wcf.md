---
title: <workflowInstanceQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 35c73f9d-474e-42eb-874d-ddc04b1987f3
ms.openlocfilehash: eaf0cd204265aac7c1421e3de0c33963e6bbb7a1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854730"
---
# <a name="workflowinstancequery-of-wcf"></a><span data-ttu-id="ecb11-102">\<workflowInstanceQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="ecb11-102">\<workflowInstanceQuery> of WCF</span></span>

<span data-ttu-id="ecb11-103">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="ecb11-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="ecb11-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ecb11-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ecb11-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ecb11-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ecb11-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="ecb11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="ecb11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="ecb11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="ecb11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="ecb11-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> workflowInstanceQueries**](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ecb11-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="ecb11-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> workflowInstanceQuery**</span><span class="sxs-lookup"><span data-stu-id="ecb11-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecb11-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecb11-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecb11-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ecb11-114">Attributes and elements</span></span>  

<span data-ttu-id="ecb11-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ecb11-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecb11-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ecb11-116">Attributes</span></span>  

<span data-ttu-id="ecb11-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ecb11-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ecb11-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ecb11-118">Child elements</span></span>  
  
|<span data-ttu-id="ecb11-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecb11-119">Element</span></span>|<span data-ttu-id="ecb11-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ecb11-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecb11-121">\<states></span><span class="sxs-lookup"><span data-stu-id="ecb11-121">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="ecb11-122">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ecb11-122">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ecb11-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ecb11-123">Parent elements</span></span>  
  
|<span data-ttu-id="ecb11-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ecb11-124">Element</span></span>|<span data-ttu-id="ecb11-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ecb11-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecb11-126">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="ecb11-126">\<workflowInstanceQueries></span></span>](workflowinstancequeries-of-wcf.md)|<span data-ttu-id="ecb11-127">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="ecb11-127">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecb11-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecb11-128">Remarks</span></span>  

<span data-ttu-id="ecb11-129"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="ecb11-129">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="ecb11-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecb11-130">Example</span></span>  

<span data-ttu-id="ecb11-131">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="ecb11-131">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="ecb11-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ecb11-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ecb11-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ecb11-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ecb11-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ecb11-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
