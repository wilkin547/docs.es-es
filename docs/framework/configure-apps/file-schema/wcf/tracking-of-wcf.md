---
title: <tracking> de WCF
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: 4aac9f28de746e2a75a079cbaf774f01f4a08fca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135829"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="f1f92-102">\<seguimiento > de WCF</span><span class="sxs-lookup"><span data-stu-id="f1f92-102">\<tracking> of WCF</span></span>
<span data-ttu-id="f1f92-103">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="f1f92-104">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [configuración del seguimiento para un flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f1f92-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="f1f92-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f1f92-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f1f92-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f1f92-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f92-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1f92-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1f92-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f1f92-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f1f92-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f1f92-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1f92-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="f1f92-110">Attributes</span></span>  
 <span data-ttu-id="f1f92-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f1f92-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1f92-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f1f92-112">Child Elements</span></span>  
  
|<span data-ttu-id="f1f92-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1f92-113">Element</span></span>|<span data-ttu-id="f1f92-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1f92-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f1f92-115">\<participants></span><span class="sxs-lookup"><span data-stu-id="f1f92-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="f1f92-116">Una colección de elementos de configuración que definen a participantes que suscribirse a registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f1f92-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="f1f92-117">Los participantes de seguimiento contienen la lógica para procesar la carga de los registros de seguimiento (por ejemplo, podrían escribir en un archivo).</span><span class="sxs-lookup"><span data-stu-id="f1f92-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="f1f92-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f1f92-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="f1f92-119">Un perfil de seguimiento para filtrar registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1f92-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f1f92-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f1f92-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="f1f92-121">Element</span></span>|<span data-ttu-id="f1f92-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1f92-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f1f92-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f1f92-123">system.ServiceModel</span></span>|<span data-ttu-id="f1f92-124">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1f92-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1f92-125">Remarks</span></span>  
 <span data-ttu-id="f1f92-126">El seguimiento ofrece la posibilidad de examinar la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="f1f92-127">La infraestructura de seguimiento del flujo de trabajo instrumenta un flujo de trabajo para emitir registros que reflejan los eventos clave durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="f1f92-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="f1f92-128">Por ejemplo, cuando una instancia de flujo de trabajo se inicia o completa, se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f1f92-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="f1f92-129">El seguimiento también puede extraer datos comerciales relevantes asociados a las variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="f1f92-130">Por ejemplo, si el flujo de trabajo representa un sistema de procesamiento de pedidos, el Id. del pedido se puede extraer junto con el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f1f92-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="f1f92-131">En general, la habilitación del seguimiento de WF facilita el diagnóstico o los análisis comerciales durante la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f1f92-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f92-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1f92-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="f1f92-133">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f1f92-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
