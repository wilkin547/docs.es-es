---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 79230c65d8eb8c15cef5dce73698448ca7b1e003
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947310"
---
# <a name="tracking"></a><span data-ttu-id="98248-101">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="98248-101">\<tracking></span></span>
<span data-ttu-id="98248-102">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="98248-103">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento del flujo de trabajo y [configuración del seguimiento para un flujo de trabajo](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="98248-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="98248-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="98248-104">\<system.serviceModel></span></span>  
<span data-ttu-id="98248-105">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="98248-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98248-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98248-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98248-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="98248-107">Attributes and Elements</span></span>  
 <span data-ttu-id="98248-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="98248-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98248-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="98248-109">Attributes</span></span>  
 <span data-ttu-id="98248-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="98248-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="98248-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="98248-111">Child Elements</span></span>  
  
|<span data-ttu-id="98248-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="98248-112">Element</span></span>|<span data-ttu-id="98248-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="98248-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98248-114">\<participantes ></span><span class="sxs-lookup"><span data-stu-id="98248-114">\<participants></span></span>](participants.md)|<span data-ttu-id="98248-115">Colección de elementos de configuración que definen los participantes que se suscriben a los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="98248-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="98248-116">Los participantes de seguimiento contienen la lógica para procesar la carga de los registros de seguimiento (por ejemplo, podrían escribir en un archivo).</span><span class="sxs-lookup"><span data-stu-id="98248-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="98248-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="98248-117">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="98248-118">Un perfil de seguimiento para filtrar registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="98248-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="98248-119">Parent Elements</span></span>  
  
|<span data-ttu-id="98248-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="98248-120">Element</span></span>|<span data-ttu-id="98248-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="98248-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98248-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="98248-122">system.ServiceModel</span></span>|<span data-ttu-id="98248-123">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98248-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98248-124">Remarks</span></span>  
 <span data-ttu-id="98248-125">El seguimiento ofrece la posibilidad de examinar la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="98248-126">La infraestructura de seguimiento del flujo de trabajo instrumenta un flujo de trabajo para emitir registros que reflejan los eventos clave durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="98248-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="98248-127">Por ejemplo, cuando una instancia de flujo de trabajo se inicia o completa, se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="98248-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="98248-128">El seguimiento también puede extraer datos comerciales relevantes asociados a las variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="98248-129">Por ejemplo, si el flujo de trabajo representa un sistema de procesamiento de pedidos, el Id. del pedido se puede extraer junto con el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="98248-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="98248-130">En general, la habilitación del seguimiento de WF facilita el diagnóstico o los análisis comerciales durante la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="98248-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98248-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="98248-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="98248-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="98248-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
