---
title: <trackingProfile>de WCF
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 79326322eeed1f6b73729da675eb02fe6de670df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932349"
---
# <a name="trackingprofile-of-wcf"></a><span data-ttu-id="632f6-102">\<trackingProfile > de WCF</span><span class="sxs-lookup"><span data-stu-id="632f6-102">\<trackingProfile> of WCF</span></span>
<span data-ttu-id="632f6-103">Representa una sección de configuración para crear una suscripción a los registros de seguimiento de flujo de trabajo en un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="632f6-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="632f6-104">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="632f6-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="632f6-105">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="632f6-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="632f6-106">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento de flujos de trabajo y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="632f6-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="632f6-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="632f6-107">\<system.serviceModel></span></span>  
<span data-ttu-id="632f6-108">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="632f6-108">\<tracking></span></span>  
<span data-ttu-id="632f6-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="632f6-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="632f6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="632f6-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String" />
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String">
              <arguments>
                <argument name="String" />
              </arguments>
              <states>
                <state name="String" />
              </states>
              <variables>
                <variable name="String" />
              </variables>
            </activityStateQuery>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestedQueries>
            <cancelRequestedQuery activityName="String"
                                  childActivityName="String" />
          </cancelRequestedQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String"
                                 name="String" />
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery faultSourceActivityName="String"
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <stateMachineStateQueries>
            <stateMachineStateQuery activityName="String" />
          </stateMachineStateQueries>
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="632f6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="632f6-111">Attributes and Elements</span></span>  

<span data-ttu-id="632f6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="632f6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="632f6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="632f6-113">Attributes</span></span>  
  
|<span data-ttu-id="632f6-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="632f6-114">Attribute</span></span>|<span data-ttu-id="632f6-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="632f6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="632f6-116">Nombre</span><span class="sxs-lookup"><span data-stu-id="632f6-116">name</span></span>|<span data-ttu-id="632f6-117">Una cadena que especifica el nombre de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="632f6-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="632f6-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="632f6-118">Child Elements</span></span>  
  
|<span data-ttu-id="632f6-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="632f6-119">Element</span></span>|<span data-ttu-id="632f6-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="632f6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="632f6-121">\<participantes ></span><span class="sxs-lookup"><span data-stu-id="632f6-121">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="632f6-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="632f6-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="632f6-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="632f6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="632f6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="632f6-124">Element</span></span>|<span data-ttu-id="632f6-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="632f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="632f6-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="632f6-126">\<tracking></span></span>](../windows-workflow-foundation/tracking.md)|<span data-ttu-id="632f6-127">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="632f6-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="632f6-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="632f6-128">Remarks</span></span>  
 <span data-ttu-id="632f6-129">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="632f6-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="632f6-130">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="632f6-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="632f6-131">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="632f6-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="632f6-132">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="632f6-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="632f6-133">Hay una serie de tipos de consultas que le permiten suscribirse a distintas clases <xref:System.Activities.Tracking.TrackingRecord> de objetos.</span><span class="sxs-lookup"><span data-stu-id="632f6-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="632f6-134">Para obtener una lista completa de consultas, vea [ \<participantes >](../windows-workflow-foundation/participants.md) y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="632f6-134">For a complete list of queries, see [\<participants>](../windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="632f6-135">En el ejemplo siguiente se muestra un perfil de seguimiento en un archivo de configuración que permite a un participante `Started` de `Completed` seguimiento suscribirse a los eventos de flujo de trabajo y.</span><span class="sxs-lookup"><span data-stu-id="632f6-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <trackingProfile name="Sample Tracking Profile">
        <workflow activityDefinitionId="*">
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="Started" />
                <state name="Completed" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="632f6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="632f6-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="632f6-137">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="632f6-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="632f6-138">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="632f6-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
