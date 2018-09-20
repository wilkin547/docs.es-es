---
title: '&lt;Flujo de trabajo&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: 940d396bd6e3dc3cdc5d8fb6f72d293061f3aa0e
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46326496"
---
# <a name="ltworkflowgt"></a><span data-ttu-id="8bda6-102">&lt;Flujo de trabajo&gt;</span><span class="sxs-lookup"><span data-stu-id="8bda6-102">&lt;workflow&gt;</span></span>
<span data-ttu-id="8bda6-103">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8bda6-103">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="8bda6-104">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8bda6-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8bda6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8bda6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8bda6-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="8bda6-106">\<tracking></span></span>  
<span data-ttu-id="8bda6-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8bda6-107">\<trackingProfile></span></span>  
<span data-ttu-id="8bda6-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="8bda6-108">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bda6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bda6-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8bda6-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8bda6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8bda6-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8bda6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8bda6-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="8bda6-112">Attributes</span></span>  
  
|<span data-ttu-id="8bda6-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="8bda6-113">Attribute</span></span>|<span data-ttu-id="8bda6-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bda6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bda6-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="8bda6-115">activityDefinitionId</span></span>|<span data-ttu-id="8bda6-116">Una cadena que especifica el Id. de definición de actividad del flujo de trabajo del que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8bda6-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8bda6-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8bda6-117">Child Elements</span></span>  
  
|<span data-ttu-id="8bda6-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bda6-118">Element</span></span>|<span data-ttu-id="8bda6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bda6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bda6-120">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="8bda6-120">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="8bda6-121">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="8bda6-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8bda6-122">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="8bda6-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="8bda6-123">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="8bda6-123">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="8bda6-124">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8bda6-125">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8bda6-126">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="8bda6-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8bda6-127">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="8bda6-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="8bda6-128">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8bda6-128">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="8bda6-129">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8bda6-130">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="8bda6-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="8bda6-131">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="8bda6-131">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="8bda6-132">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="8bda6-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="8bda6-133">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="8bda6-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="8bda6-134">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8bda6-134">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="8bda6-135">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="8bda6-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8bda6-136">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="8bda6-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="8bda6-137">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="8bda6-137">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="8bda6-138">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="8bda6-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8bda6-139">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="8bda6-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="8bda6-140">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="8bda6-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="8bda6-141">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="8bda6-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="8bda6-142">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="8bda6-142">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="8bda6-143">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="8bda6-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8bda6-144">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8bda6-144">Parent Elements</span></span>  
  
|<span data-ttu-id="8bda6-145">Elemento</span><span class="sxs-lookup"><span data-stu-id="8bda6-145">Element</span></span>|<span data-ttu-id="8bda6-146">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bda6-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8bda6-147">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8bda6-147">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="8bda6-148">Representa una sección de configuración para crear una suscripción a los registros en un participante de seguimiento de seguimiento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="8bda6-149">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8bda6-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="8bda6-150">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="8bda6-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bda6-151">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bda6-151">Remarks</span></span>  
 <span data-ttu-id="8bda6-152">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una determinada instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8bda6-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="8bda6-153">Este elemento de configuración identifica la instancia de flujo de trabajo de la que se está realizando el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8bda6-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="8bda6-154">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="8bda6-155">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="8bda6-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="8bda6-156">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="8bda6-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="8bda6-157">Hay una serie de tipos de consultas que le permiten que suscribirse a las distintas clases de los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8bda6-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="8bda6-158">Para obtener una lista completa de las consultas, vea la lista de elementos secundarios de este tema y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8bda6-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="8bda6-159">El ejemplo siguiente muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento para suscribirse a la `Started` y `Completed` eventos de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8bda6-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8bda6-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bda6-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="8bda6-161">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="8bda6-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8bda6-162">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8bda6-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
