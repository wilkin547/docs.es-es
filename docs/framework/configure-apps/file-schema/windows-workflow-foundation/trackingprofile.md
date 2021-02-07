---
description: 'Más información acerca de: <trackingProfile>'
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 4e0973cb44f61340e6cec7497362627cdccbd494
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697990"
---
# \<trackingProfile>

<span data-ttu-id="a8cb6-102">Representa una sección de configuración para crear una suscripción a los registros de seguimiento del flujo de trabajo en un participante del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="a8cb6-103">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a8cb6-104">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="a8cb6-105">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento de flujos de trabajo y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a8cb6-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**  
  
## <a name="syntax"></a><span data-ttu-id="a8cb6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8cb6-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8cb6-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a8cb6-107">Attributes and Elements</span></span>  

 <span data-ttu-id="a8cb6-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8cb6-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="a8cb6-109">Attributes</span></span>  
  
|<span data-ttu-id="a8cb6-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="a8cb6-110">Attribute</span></span>|<span data-ttu-id="a8cb6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8cb6-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a8cb6-112">name</span><span class="sxs-lookup"><span data-stu-id="a8cb6-112">name</span></span>|<span data-ttu-id="a8cb6-113">Una cadena que especifica el nombre de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-113">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8cb6-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a8cb6-114">Child Elements</span></span>  
  
|<span data-ttu-id="a8cb6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8cb6-115">Element</span></span>|<span data-ttu-id="a8cb6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8cb6-116">Description</span></span>|  
|-------------|-----------------|  
|[\<participants>](participants.md)|<span data-ttu-id="a8cb6-117">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-117">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a8cb6-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a8cb6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a8cb6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a8cb6-119">Element</span></span>|<span data-ttu-id="a8cb6-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8cb6-120">Description</span></span>|  
|-------------|-----------------|  
|[\<tracking>](tracking.md)|<span data-ttu-id="a8cb6-121">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-121">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8cb6-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a8cb6-122">Remarks</span></span>  

 <span data-ttu-id="a8cb6-123">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-123">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a8cb6-124">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-124">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="a8cb6-125">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-125">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="a8cb6-126">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-126">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="a8cb6-127">Hay una serie de tipos de consultas que le permiten suscribirse a distintas clases de <xref:System.Activities.Tracking.TrackingRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-127">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="a8cb6-128">Para obtener una lista completa de consultas, vea [\<participants>](participants.md) y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a8cb6-128">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="a8cb6-129">En el ejemplo siguiente se muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento suscribirse a los `Started` `Completed` eventos de flujo de trabajo y.</span><span class="sxs-lookup"><span data-stu-id="a8cb6-129">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a8cb6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8cb6-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="a8cb6-131">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8cb6-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a8cb6-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a8cb6-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
