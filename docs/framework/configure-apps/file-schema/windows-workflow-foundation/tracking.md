---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 0b00780dedc15fe90163145f23c57f62369c401f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198748"
---
# \<tracking>

<span data-ttu-id="ba313-101">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-101">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="ba313-102">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento del flujo de trabajo y [configuración del seguimiento para un flujo de trabajo](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="ba313-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**  
  
## <a name="syntax"></a><span data-ttu-id="ba313-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba313-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba313-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba313-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ba313-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba313-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba313-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba313-106">Attributes</span></span>  

 <span data-ttu-id="ba313-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ba313-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ba313-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba313-108">Child Elements</span></span>  
  
|<span data-ttu-id="ba313-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba313-109">Element</span></span>|<span data-ttu-id="ba313-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba313-110">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="ba313-111">Una colección de elementos de configuración que definen participantes que se suscriben a los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba313-111">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="ba313-112">Los participantes de seguimiento contienen la lógica para procesar la carga de los registros de seguimiento (por ejemplo, podrían escribir en un archivo).</span><span class="sxs-lookup"><span data-stu-id="ba313-112">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="ba313-113">Un perfil de seguimiento para filtrar registros de seguimiento emitidos desde una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-113">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba313-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba313-114">Parent Elements</span></span>  
  
|<span data-ttu-id="ba313-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba313-115">Element</span></span>|<span data-ttu-id="ba313-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba313-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba313-117">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="ba313-117">system.ServiceModel</span></span>|<span data-ttu-id="ba313-118">El elemento raíz de todos los elementos de configuración de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-118">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba313-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba313-119">Remarks</span></span>  

 <span data-ttu-id="ba313-120">El seguimiento ofrece la posibilidad de examinar la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-120">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="ba313-121">La infraestructura de seguimiento del flujo de trabajo instrumenta un flujo de trabajo para emitir registros que reflejan los eventos clave durante la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba313-121">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="ba313-122">Por ejemplo, cuando una instancia de flujo de trabajo se inicia o completa, se emiten los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba313-122">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="ba313-123">El seguimiento también puede extraer datos comerciales relevantes asociados a las variables de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-123">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="ba313-124">Por ejemplo, si el flujo de trabajo representa un sistema de procesamiento de pedidos, el Id. del pedido se puede extraer junto con el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba313-124">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="ba313-125">En general, la habilitación del seguimiento de WF facilita el diagnóstico o los análisis comerciales durante la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ba313-125">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba313-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba313-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="ba313-127">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ba313-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
