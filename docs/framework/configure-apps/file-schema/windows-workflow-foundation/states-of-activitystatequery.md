---
title: '&lt;estados&gt; de &lt;activityStateQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4df89af05ae341a981c3b4f34ba919bb445d724e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt-of-ltactivitystatequerygt"></a><span data-ttu-id="d05f2-102">&lt;estados&gt; de &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d05f2-102">&lt;states&gt; of &lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="d05f2-103">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d05f2-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="d05f2-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d05f2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d05f2-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d05f2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d05f2-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="d05f2-106">\<tracking></span></span>  
<span data-ttu-id="d05f2-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d05f2-107">\<trackingProfile></span></span>  
<span data-ttu-id="d05f2-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="d05f2-108">\<workflow></span></span>  
<span data-ttu-id="d05f2-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="d05f2-109">\<activityStateQueries></span></span>  
<span data-ttu-id="d05f2-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="d05f2-110">\<activityStateQuery></span></span>  
<span data-ttu-id="d05f2-111">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="d05f2-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05f2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d05f2-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d05f2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d05f2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d05f2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d05f2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d05f2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="d05f2-115">Attributes</span></span>  
 <span data-ttu-id="d05f2-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d05f2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d05f2-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d05f2-117">Child Elements</span></span>  
  
|<span data-ttu-id="d05f2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="d05f2-118">Element</span></span>|<span data-ttu-id="d05f2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="d05f2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d05f2-120">\<estado ></span><span class="sxs-lookup"><span data-stu-id="d05f2-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="d05f2-121">Un elemento de configuración que contiene los estados de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d05f2-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d05f2-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d05f2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d05f2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d05f2-123">Element</span></span>|<span data-ttu-id="d05f2-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="d05f2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d05f2-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="d05f2-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="d05f2-126">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d05f2-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d05f2-127">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d05f2-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d05f2-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d05f2-128">Remarks</span></span>  
 <span data-ttu-id="d05f2-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d05f2-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d05f2-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d05f2-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d05f2-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d05f2-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d05f2-132">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="d05f2-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d05f2-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="d05f2-133">See Also</span></span>  
 <span data-ttu-id="d05f2-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d05f2-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="d05f2-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d05f2-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="d05f2-136">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d05f2-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d05f2-137">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d05f2-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
