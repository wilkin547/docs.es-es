---
title: '&lt;trackingProfile&gt; de WCF'
ms.date: 10/08/2018
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: a35b91867464b48b5e5ea858bca18296cb2d903a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629555"
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="0c164-102">&lt;trackingProfile&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="0c164-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="0c164-103">Representa una sección de configuración para crear una suscripción a los registros en un participante de seguimiento de seguimiento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c164-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="0c164-104">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c164-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="0c164-105">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="0c164-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="0c164-106">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="0c164-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0c164-107">\<system.serviceModel></span></span>  
<span data-ttu-id="0c164-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="0c164-108">\<tracking></span></span>  
<span data-ttu-id="0c164-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0c164-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c164-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c164-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c164-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c164-111">Attributes and Elements</span></span>  

<span data-ttu-id="0c164-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c164-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c164-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c164-113">Attributes</span></span>  
  
|<span data-ttu-id="0c164-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="0c164-114">Attribute</span></span>|<span data-ttu-id="0c164-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c164-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c164-116">name</span><span class="sxs-lookup"><span data-stu-id="0c164-116">name</span></span>|<span data-ttu-id="0c164-117">Una cadena que especifica el nombre de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c164-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c164-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c164-118">Child Elements</span></span>  
  
|<span data-ttu-id="0c164-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c164-119">Element</span></span>|<span data-ttu-id="0c164-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c164-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c164-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="0c164-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="0c164-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0c164-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c164-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c164-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0c164-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c164-124">Element</span></span>|<span data-ttu-id="0c164-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c164-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c164-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="0c164-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="0c164-127">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c164-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c164-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c164-128">Remarks</span></span>  
 <span data-ttu-id="0c164-129">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c164-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="0c164-130">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c164-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="0c164-131">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0c164-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="0c164-132">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="0c164-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="0c164-133">Hay una serie de tipos de consultas que le permiten suscribirse a las distintas clases de <xref:System.Activities.Tracking.TrackingRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="0c164-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="0c164-134">Para obtener una lista completa de las consultas, vea [ \<participantes >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="0c164-135">El ejemplo siguiente muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento para suscribirse a la `Started` y `Completed` eventos de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c164-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c164-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c164-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="0c164-137">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c164-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0c164-138">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0c164-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
