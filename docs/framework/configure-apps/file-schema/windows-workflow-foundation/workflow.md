---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: fdfaf234b5dda5703da7fc1ca1fe4554d57405f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148690"
---
# \<workflow>

<span data-ttu-id="80cca-101">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80cca-101">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="80cca-102">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento de flujos de trabajo y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="80cca-102">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflow>**  
  
## <a name="syntax"></a><span data-ttu-id="80cca-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80cca-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80cca-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80cca-104">Attributes and Elements</span></span>  

 <span data-ttu-id="80cca-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80cca-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80cca-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="80cca-106">Attributes</span></span>  
  
|<span data-ttu-id="80cca-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="80cca-107">Attribute</span></span>|<span data-ttu-id="80cca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cca-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80cca-109">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="80cca-109">activityDefinitionId</span></span>|<span data-ttu-id="80cca-110">Una cadena que especifica el Id. de definición de actividad del flujo de trabajo del que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="80cca-110">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80cca-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80cca-111">Child Elements</span></span>  
  
|<span data-ttu-id="80cca-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="80cca-112">Element</span></span>|<span data-ttu-id="80cca-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cca-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries.md)|<span data-ttu-id="80cca-114">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80cca-114">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="80cca-115">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="80cca-115">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[\<activityStateQueries>](activitystatequeries.md)|<span data-ttu-id="80cca-116">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cca-116">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="80cca-117">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cca-117">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="80cca-118">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="80cca-118">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="80cca-119">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="80cca-119">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="80cca-120">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cca-120">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="80cca-121">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="80cca-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[\<cancelRequestedQueries>](cancelrequestedqueries.md)|<span data-ttu-id="80cca-122">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80cca-122">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="80cca-123">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="80cca-123">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[\<customTrackingQueries>](customtrackingqueries.md)|<span data-ttu-id="80cca-124">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="80cca-124">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="80cca-125">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="80cca-125">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="80cca-126">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="80cca-126">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="80cca-127">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="80cca-127">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="80cca-128">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="80cca-128">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="80cca-129">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="80cca-129">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[\<workflowInstanceQueries>](workflowinstancequeries.md)|<span data-ttu-id="80cca-130">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="80cca-130">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80cca-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80cca-131">Parent Elements</span></span>  
  
|<span data-ttu-id="80cca-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="80cca-132">Element</span></span>|<span data-ttu-id="80cca-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cca-133">Description</span></span>|  
|-------------|-----------------|  
|[\<trackingProfile>](trackingprofile.md)|<span data-ttu-id="80cca-134">Representa una sección de configuración para crear una suscripción a los registros de seguimiento del flujo de trabajo en un participante del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="80cca-134">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="80cca-135">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80cca-135">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="80cca-136">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="80cca-136">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80cca-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80cca-137">Remarks</span></span>  

 <span data-ttu-id="80cca-138">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una determinada instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="80cca-138">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="80cca-139">Este elemento de configuración identifica la instancia de flujo de trabajo de la que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="80cca-139">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="80cca-140">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80cca-140">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="80cca-141">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="80cca-141">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="80cca-142">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="80cca-142">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="80cca-143">Hay muchos tipos de consultas que le permiten suscribirse a distintas clases de registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="80cca-143">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="80cca-144">Para obtener una lista completa de consultas, vea la lista de elementos secundarios de este tema y [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="80cca-144">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="80cca-145">En el ejemplo siguiente se muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento suscribirse a los `Started` `Completed` eventos de flujo de trabajo y.</span><span class="sxs-lookup"><span data-stu-id="80cca-145">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80cca-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="80cca-146">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="80cca-147">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="80cca-147">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80cca-148">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="80cca-148">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
