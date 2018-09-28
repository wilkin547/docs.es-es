---
title: '&lt;trackingProfile&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: 34497c8e27f56adce12fa358620d3d3f8fe54e48
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "47424251"
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="a6fea-102">&lt;trackingProfile&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="a6fea-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="a6fea-103">Representa una sección de configuración para crear una suscripción a los registros en un participante de seguimiento de seguimiento del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6fea-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="a6fea-104">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6fea-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a6fea-105">Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.</span><span class="sxs-lookup"><span data-stu-id="a6fea-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="a6fea-106">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a6fea-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="a6fea-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a6fea-107">\<system.serviceModel></span></span>  
<span data-ttu-id="a6fea-108">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="a6fea-108">\<tracking></span></span>  
<span data-ttu-id="a6fea-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="a6fea-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6fea-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6fea-110">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>      <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>    
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6fea-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a6fea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a6fea-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a6fea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6fea-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a6fea-113">Attributes</span></span>  
  
|<span data-ttu-id="a6fea-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="a6fea-114">Attribute</span></span>|<span data-ttu-id="a6fea-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6fea-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6fea-116">name</span><span class="sxs-lookup"><span data-stu-id="a6fea-116">name</span></span>|<span data-ttu-id="a6fea-117">Una cadena que especifica el nombre de un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a6fea-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6fea-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a6fea-118">Child Elements</span></span>  
  
|<span data-ttu-id="a6fea-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6fea-119">Element</span></span>|<span data-ttu-id="a6fea-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6fea-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6fea-121">\<los participantes ></span><span class="sxs-lookup"><span data-stu-id="a6fea-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="a6fea-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="a6fea-122">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6fea-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a6fea-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a6fea-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a6fea-124">Element</span></span>|<span data-ttu-id="a6fea-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6fea-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6fea-126">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="a6fea-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="a6fea-127">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6fea-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6fea-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6fea-128">Remarks</span></span>  
 <span data-ttu-id="a6fea-129">Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6fea-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="a6fea-130">Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6fea-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="a6fea-131">A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="a6fea-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="a6fea-132">Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.</span><span class="sxs-lookup"><span data-stu-id="a6fea-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="a6fea-133">Hay una serie de tipos de consultas que le permiten suscribirse a las distintas clases de <xref:System.Activities.Tracking.TrackingRecord> objetos.</span><span class="sxs-lookup"><span data-stu-id="a6fea-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="a6fea-134">Para obtener una lista completa de las consultas, vea [ \<participantes >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) y [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="a6fea-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="a6fea-135">El ejemplo siguiente muestra un perfil de seguimiento en un archivo de configuración que permite a un participante de seguimiento para suscribirse a la `Started` y `Completed` eventos de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a6fea-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6fea-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="a6fea-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="a6fea-137">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a6fea-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a6fea-138">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a6fea-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
