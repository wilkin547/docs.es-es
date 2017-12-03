---
title: '&lt;activityStateQuery&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e6621a0f60a6dc916fa1ee34841946929623be88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="665f1-102">&lt;activityStateQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="665f1-102">&lt;activityStateQuery&gt; of WCF</span></span>
<span data-ttu-id="665f1-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="665f1-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="665f1-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se completa la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="665f1-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="665f1-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="665f1-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="665f1-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="665f1-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="665f1-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="665f1-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="665f1-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="665f1-108">\<system.serviceModel></span></span>  
<span data-ttu-id="665f1-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="665f1-109">\<tracking></span></span>  
<span data-ttu-id="665f1-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="665f1-110">\<trackingProfile></span></span>  
<span data-ttu-id="665f1-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="665f1-111">\<workflow></span></span>  
<span data-ttu-id="665f1-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="665f1-112">\<activityStateQueries></span></span>  
<span data-ttu-id="665f1-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="665f1-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="665f1-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="665f1-114">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="665f1-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="665f1-115">Attributes and Elements</span></span>  
 <span data-ttu-id="665f1-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="665f1-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="665f1-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="665f1-117">Attributes</span></span>  
  
|<span data-ttu-id="665f1-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="665f1-118">Attribute</span></span>|<span data-ttu-id="665f1-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="665f1-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="665f1-120">activityName</span><span class="sxs-lookup"><span data-stu-id="665f1-120">activityName</span></span>|<span data-ttu-id="665f1-121">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="665f1-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="665f1-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="665f1-122">Child Elements</span></span>  
  
|<span data-ttu-id="665f1-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="665f1-123">Element</span></span>|<span data-ttu-id="665f1-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="665f1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="665f1-125">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="665f1-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="665f1-126">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="665f1-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="665f1-127">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="665f1-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="665f1-128">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="665f1-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="665f1-129">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="665f1-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="665f1-130">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="665f1-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="665f1-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="665f1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="665f1-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="665f1-132">Element</span></span>|<span data-ttu-id="665f1-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="665f1-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="665f1-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="665f1-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="665f1-135">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="665f1-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="665f1-136">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="665f1-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="665f1-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="665f1-137">Remarks</span></span>  
 <span data-ttu-id="665f1-138">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="665f1-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="665f1-139">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="665f1-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="665f1-140">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="665f1-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="665f1-141">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="665f1-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="665f1-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="665f1-142">See Also</span></span>  
 <span data-ttu-id="665f1-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span><span class="sxs-lookup"><span data-stu-id="665f1-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span></span>    
 <span data-ttu-id="665f1-144"><xref:System.Activities.Tracking.ActivityStateQuery></span><span class="sxs-lookup"><span data-stu-id="665f1-144"><xref:System.Activities.Tracking.ActivityStateQuery></span></span>     
 [<span data-ttu-id="665f1-145">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="665f1-145">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="665f1-146">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="665f1-146">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
