---
title: <activityStateQuery> de WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704536"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="2c30f-102">\<activityStateQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="2c30f-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="2c30f-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c30f-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="2c30f-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c30f-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="2c30f-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="2c30f-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="2c30f-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="2c30f-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="2c30f-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2c30f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="2c30f-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="2c30f-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="2c30f-109">\<profiles> \<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2c30f-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="2c30f-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="2c30f-110">\<workflow></span></span>  
<span data-ttu-id="2c30f-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2c30f-111">\<activityStateQueries></span></span>  
<span data-ttu-id="2c30f-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2c30f-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c30f-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c30f-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c30f-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2c30f-114">Attributes and elements</span></span>  

<span data-ttu-id="2c30f-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2c30f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c30f-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="2c30f-116">Attributes</span></span>  
  
|<span data-ttu-id="2c30f-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="2c30f-117">Attribute</span></span>|<span data-ttu-id="2c30f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c30f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2c30f-119">activityName</span><span class="sxs-lookup"><span data-stu-id="2c30f-119">activityName</span></span>|<span data-ttu-id="2c30f-120">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="2c30f-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c30f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2c30f-121">Child elements</span></span>  
  
|<span data-ttu-id="2c30f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c30f-122">Element</span></span>|<span data-ttu-id="2c30f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c30f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c30f-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="2c30f-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="2c30f-125">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="2c30f-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="2c30f-126">\<states></span><span class="sxs-lookup"><span data-stu-id="2c30f-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2c30f-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2c30f-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="2c30f-128">\<states></span><span class="sxs-lookup"><span data-stu-id="2c30f-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="2c30f-129">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="2c30f-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c30f-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2c30f-130">Parent elements</span></span>  
  
|<span data-ttu-id="2c30f-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="2c30f-131">Element</span></span>|<span data-ttu-id="2c30f-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c30f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2c30f-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="2c30f-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2c30f-134">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2c30f-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2c30f-135">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2c30f-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c30f-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2c30f-136">Remarks</span></span>

<span data-ttu-id="2c30f-137">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c30f-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2c30f-138">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2c30f-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2c30f-139">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. El ejemplo siguiente muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera el registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2c30f-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2c30f-140">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="2c30f-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c30f-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c30f-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="2c30f-142">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c30f-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2c30f-143">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2c30f-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
