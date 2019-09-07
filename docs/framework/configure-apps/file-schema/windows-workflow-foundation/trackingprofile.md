---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 3120d6f5d1bb5a5cf452567e96766231534f3f41
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398588"
---
# <a name="trackingprofile"></a><span data-ttu-id="5d86e-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5d86e-101">\<trackingProfile></span></span>
<span data-ttu-id="5d86e-102">Representa una sección de configuración para crear una suscripción a los registros de seguimiento de flujo de trabajo en un participante de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5d86e-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="5d86e-103">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5d86e-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="5d86e-104">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="5d86e-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="5d86e-105">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento de flujos de trabajo y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5d86e-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5d86e-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5d86e-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5d86e-107">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5d86e-107">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5d86e-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5d86e-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5d86e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> trackingProfile**</span><span class="sxs-lookup"><span data-stu-id="5d86e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<trackingProfile>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d86e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d86e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d86e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5d86e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d86e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5d86e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d86e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5d86e-113">Attributes</span></span>  
  
|<span data-ttu-id="5d86e-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5d86e-114">Attribute</span></span>|<span data-ttu-id="5d86e-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d86e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d86e-116">name</span><span class="sxs-lookup"><span data-stu-id="5d86e-116">name</span></span>|<span data-ttu-id="5d86e-117">Una cadena que especifica el nombre de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5d86e-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d86e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5d86e-118">Child Elements</span></span>  
  
|<span data-ttu-id="5d86e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d86e-119">Element</span></span>|<span data-ttu-id="5d86e-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d86e-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d86e-121">\<participantes ></span><span class="sxs-lookup"><span data-stu-id="5d86e-121">\<participants></span></span>](participants.md)|<span data-ttu-id="5d86e-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5d86e-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d86e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5d86e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5d86e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5d86e-124">Element</span></span>|<span data-ttu-id="5d86e-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5d86e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d86e-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5d86e-126">\<tracking></span></span>](tracking.md)|<span data-ttu-id="5d86e-127">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d86e-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d86e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d86e-128">Remarks</span></span>  
 <span data-ttu-id="5d86e-129">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5d86e-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="5d86e-130">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d86e-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="5d86e-131">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="5d86e-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="5d86e-132">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="5d86e-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="5d86e-133">Hay una serie de tipos de consultas que le permiten suscribirse a distintas clases <xref:System.Activities.Tracking.TrackingRecord> de objetos.</span><span class="sxs-lookup"><span data-stu-id="5d86e-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="5d86e-134">Para obtener una lista completa de consultas, vea [ \<participantes >](participants.md) y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5d86e-134">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="5d86e-135">En el ejemplo siguiente se muestra un perfil de seguimiento en un archivo de configuración que permite a un participante `Started` de `Completed` seguimiento suscribirse a los eventos de flujo de trabajo y.</span><span class="sxs-lookup"><span data-stu-id="5d86e-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5d86e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d86e-136">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="5d86e-137">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d86e-137">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5d86e-138">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5d86e-138">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
