---
title: <workflow>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: d6c23bb0b819b5f22367a93db0dec64787449664
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136189"
---
# <a name="workflow"></a><span data-ttu-id="7d0c7-101">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="7d0c7-101">\<workflow></span></span>
<span data-ttu-id="7d0c7-102">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-102">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="7d0c7-103">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d0c7-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7d0c7-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d0c7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7d0c7-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="7d0c7-105">\<tracking></span></span>  
<span data-ttu-id="7d0c7-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7d0c7-106">\<trackingProfile></span></span>  
<span data-ttu-id="7d0c7-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="7d0c7-107">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d0c7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d0c7-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d0c7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7d0c7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7d0c7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d0c7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7d0c7-111">Attributes</span></span>  
  
|<span data-ttu-id="7d0c7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7d0c7-112">Attribute</span></span>|<span data-ttu-id="7d0c7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d0c7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7d0c7-114">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="7d0c7-114">activityDefinitionId</span></span>|<span data-ttu-id="7d0c7-115">Una cadena que especifica el Id. de definición de actividad del flujo de trabajo del que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-115">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d0c7-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7d0c7-116">Child Elements</span></span>  
  
|<span data-ttu-id="7d0c7-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d0c7-117">Element</span></span>|<span data-ttu-id="7d0c7-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d0c7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d0c7-119">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-119">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="7d0c7-120">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-120">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7d0c7-121">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-121">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="7d0c7-122">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-122">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="7d0c7-123">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-123">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="7d0c7-124">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-124">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="7d0c7-125">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-125">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="7d0c7-126">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-126">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="7d0c7-127">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-127">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="7d0c7-128">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-128">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7d0c7-129">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-129">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="7d0c7-130">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-130">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="7d0c7-131">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-131">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7d0c7-132">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-132">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="7d0c7-133">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-133">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="7d0c7-134">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-134">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7d0c7-135">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-135">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="7d0c7-136">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-136">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="7d0c7-137">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-137">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="7d0c7-138">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-138">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="7d0c7-139">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-139">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="7d0c7-140">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-140">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="7d0c7-141">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="7d0c7-141">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="7d0c7-142">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-142">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d0c7-143">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7d0c7-143">Parent Elements</span></span>  
  
|<span data-ttu-id="7d0c7-144">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d0c7-144">Element</span></span>|<span data-ttu-id="7d0c7-145">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d0c7-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d0c7-146">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7d0c7-146">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="7d0c7-147">Representa una sección de configuración para crear una suscripción a los registros en un participante de seguimiento de seguimiento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-147">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="7d0c7-148">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-148">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="7d0c7-149">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-149">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d0c7-150">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d0c7-150">Remarks</span></span>  
 <span data-ttu-id="7d0c7-151">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una determinada instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-151">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="7d0c7-152">Este elemento de configuración identifica la instancia de flujo de trabajo de la que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-152">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="7d0c7-153">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-153">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="7d0c7-154">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-154">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="7d0c7-155">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-155">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="7d0c7-156">Hay una serie de tipos de consultas que le permiten que suscribirse a las distintas clases de los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-156">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="7d0c7-157">Para obtener una lista completa de las consultas, vea la lista de elementos secundarios de este tema y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7d0c7-157">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="7d0c7-158">El ejemplo siguiente muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento para suscribirse a la `Started` y `Completed` eventos de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d0c7-158">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d0c7-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d0c7-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="7d0c7-160">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="7d0c7-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7d0c7-161">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7d0c7-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
