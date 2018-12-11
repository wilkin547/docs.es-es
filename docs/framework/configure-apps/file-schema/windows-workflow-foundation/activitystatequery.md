---
title: '&lt;activityStateQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 3c6243e6b8e1d2b32dc830609a5d4df474f48e61
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151179"
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="20fc6-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="20fc6-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="20fc6-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20fc6-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="20fc6-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20fc6-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="20fc6-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="20fc6-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="20fc6-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="20fc6-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="20fc6-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="20fc6-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="20fc6-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="20fc6-108">\<system.serviceModel></span></span>  
<span data-ttu-id="20fc6-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="20fc6-109">\<tracking></span></span>  
<span data-ttu-id="20fc6-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="20fc6-110">\<trackingProfile></span></span>  
<span data-ttu-id="20fc6-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="20fc6-111">\<workflow></span></span>  
<span data-ttu-id="20fc6-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="20fc6-112">\<activityStateQueries></span></span>  
<span data-ttu-id="20fc6-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="20fc6-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20fc6-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20fc6-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20fc6-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20fc6-115">Attributes and Elements</span></span>  
 <span data-ttu-id="20fc6-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20fc6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20fc6-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="20fc6-117">Attributes</span></span>  
  
|<span data-ttu-id="20fc6-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="20fc6-118">Attribute</span></span>|<span data-ttu-id="20fc6-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="20fc6-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20fc6-120">activityName</span><span class="sxs-lookup"><span data-stu-id="20fc6-120">activityName</span></span>|<span data-ttu-id="20fc6-121">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="20fc6-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20fc6-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20fc6-122">Child Elements</span></span>  
  
|<span data-ttu-id="20fc6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="20fc6-123">Element</span></span>|<span data-ttu-id="20fc6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="20fc6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20fc6-125">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="20fc6-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="20fc6-126">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="20fc6-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="20fc6-127">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="20fc6-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="20fc6-128">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="20fc6-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="20fc6-129">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="20fc6-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="20fc6-130">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="20fc6-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20fc6-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20fc6-131">Parent Elements</span></span>  
  
|<span data-ttu-id="20fc6-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="20fc6-132">Element</span></span>|<span data-ttu-id="20fc6-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="20fc6-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20fc6-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="20fc6-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="20fc6-135">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="20fc6-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="20fc6-136">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="20fc6-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20fc6-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="20fc6-137">Remarks</span></span>  
 <span data-ttu-id="20fc6-138">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20fc6-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="20fc6-139">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="20fc6-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="20fc6-140">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="20fc6-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="20fc6-141">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="20fc6-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="20fc6-142">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="20fc6-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20fc6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="20fc6-143">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="20fc6-144">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="20fc6-144">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="20fc6-145">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="20fc6-145">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
