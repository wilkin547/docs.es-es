---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 968cfa8e5402458afd6f13545ed999a472adf2e0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151915"
---
# <a name="tracking"></a><span data-ttu-id="8dee2-101">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8dee2-101">\<tracking></span></span>
<span data-ttu-id="8dee2-102">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="8dee2-103">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, vea [Seguimiento y seguimiento](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) del flujo de trabajo y Configuración del seguimiento de un flujo de [trabajo](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="8dee2-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="8dee2-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8dee2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8dee2-105">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8dee2-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8dee2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<seguimiento>**</span><span class="sxs-lookup"><span data-stu-id="8dee2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dee2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8dee2-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String"
             profileName="String"
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String"
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8dee2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8dee2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8dee2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8dee2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8dee2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="8dee2-110">Attributes</span></span>  
 <span data-ttu-id="8dee2-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8dee2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8dee2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8dee2-112">Child Elements</span></span>  
  
|<span data-ttu-id="8dee2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="8dee2-113">Element</span></span>|<span data-ttu-id="8dee2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dee2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8dee2-115">\<participantes></span><span class="sxs-lookup"><span data-stu-id="8dee2-115">\<participants></span></span>](participants.md)|<span data-ttu-id="8dee2-116">Una colección de elementos de configuración que definen participantes que se suscriben a los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8dee2-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="8dee2-117">Los participantes de seguimiento contienen la lógica para procesar la carga de los registros de seguimiento (por ejemplo, podrían escribir en un archivo).</span><span class="sxs-lookup"><span data-stu-id="8dee2-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="8dee2-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8dee2-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="8dee2-119">Un perfil de seguimiento para filtrar registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8dee2-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8dee2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8dee2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="8dee2-121">Element</span></span>|<span data-ttu-id="8dee2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="8dee2-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dee2-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="8dee2-123">system.ServiceModel</span></span>|<span data-ttu-id="8dee2-124">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dee2-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8dee2-125">Remarks</span></span>  
 <span data-ttu-id="8dee2-126">El seguimiento ofrece la posibilidad de examinar la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="8dee2-127">La infraestructura de seguimiento del flujo de trabajo instrumenta un flujo de trabajo para emitir registros que reflejan los eventos clave durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8dee2-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="8dee2-128">Por ejemplo, cuando una instancia de flujo de trabajo se inicia o completa, se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8dee2-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="8dee2-129">El seguimiento también puede extraer datos comerciales relevantes asociados a las variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="8dee2-130">Por ejemplo, si el flujo de trabajo representa un sistema de procesamiento de pedidos, el Id. del pedido se puede extraer junto con el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8dee2-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="8dee2-131">En general, la habilitación del seguimiento de WF facilita el diagnóstico o los análisis comerciales durante la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8dee2-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dee2-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8dee2-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="8dee2-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="8dee2-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
