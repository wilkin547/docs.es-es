---
title: '&lt;activityStateQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 6d55a53a6344922cee0d42c26102d5f0bbf46f67
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151796"
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="288b8-102">&lt;activityStateQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="288b8-102">&lt;activityStateQuery&gt; of WCF</span></span>

<span data-ttu-id="288b8-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="288b8-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="288b8-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="288b8-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="288b8-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="288b8-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="288b8-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="288b8-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="288b8-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="288b8-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="288b8-108">\<system.serviceModel > \<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="288b8-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="288b8-109">\<perfiles > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="288b8-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="288b8-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="288b8-110">\<workflow></span></span>  
<span data-ttu-id="288b8-111">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="288b8-111">\<activityStateQueries></span></span>  
<span data-ttu-id="288b8-112">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="288b8-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288b8-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="288b8-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
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
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="288b8-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="288b8-114">Attributes and elements</span></span>  

<span data-ttu-id="288b8-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="288b8-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="288b8-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="288b8-116">Attributes</span></span>  
  
|<span data-ttu-id="288b8-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="288b8-117">Attribute</span></span>|<span data-ttu-id="288b8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="288b8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="288b8-119">activityName</span><span class="sxs-lookup"><span data-stu-id="288b8-119">activityName</span></span>|<span data-ttu-id="288b8-120">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="288b8-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="288b8-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="288b8-121">Child elements</span></span>  
  
|<span data-ttu-id="288b8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="288b8-122">Element</span></span>|<span data-ttu-id="288b8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="288b8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="288b8-124">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="288b8-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="288b8-125">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="288b8-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="288b8-126">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="288b8-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="288b8-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="288b8-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="288b8-128">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="288b8-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="288b8-129">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="288b8-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="288b8-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="288b8-130">Parent elements</span></span>  
  
|<span data-ttu-id="288b8-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="288b8-131">Element</span></span>|<span data-ttu-id="288b8-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="288b8-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="288b8-133">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="288b8-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="288b8-134">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="288b8-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="288b8-135">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="288b8-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="288b8-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="288b8-136">Remarks</span></span>

<span data-ttu-id="288b8-137">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="288b8-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="288b8-138">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="288b8-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="288b8-139">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. El ejemplo siguiente muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="288b8-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="288b8-140">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="288b8-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="288b8-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="288b8-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="288b8-142">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="288b8-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="288b8-143">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="288b8-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
