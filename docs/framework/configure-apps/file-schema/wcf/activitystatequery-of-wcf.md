---
title: <activityStateQuery>de WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: ce7505896b9c5bb605bb0f67d735cb324f4fd493
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926896"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="25071-102">\<activityStateQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="25071-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="25071-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="25071-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="25071-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="25071-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="25071-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="25071-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="25071-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="25071-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="25071-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="25071-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="25071-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="25071-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="25071-109">\<perfiles > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="25071-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="25071-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="25071-110">\<workflow></span></span>  
<span data-ttu-id="25071-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="25071-111">\<activityStateQueries></span></span>  
<span data-ttu-id="25071-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="25071-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25071-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25071-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25071-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="25071-114">Attributes and elements</span></span>  

<span data-ttu-id="25071-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="25071-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25071-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="25071-116">Attributes</span></span>  
  
|<span data-ttu-id="25071-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="25071-117">Attribute</span></span>|<span data-ttu-id="25071-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25071-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25071-119">activityName</span><span class="sxs-lookup"><span data-stu-id="25071-119">activityName</span></span>|<span data-ttu-id="25071-120">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="25071-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25071-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="25071-121">Child elements</span></span>  
  
|<span data-ttu-id="25071-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="25071-122">Element</span></span>|<span data-ttu-id="25071-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25071-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25071-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="25071-124">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="25071-125">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="25071-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="25071-126">\<states></span><span class="sxs-lookup"><span data-stu-id="25071-126">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="25071-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="25071-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="25071-128">\<states></span><span class="sxs-lookup"><span data-stu-id="25071-128">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="25071-129">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="25071-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="25071-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="25071-130">Parent elements</span></span>  
  
|<span data-ttu-id="25071-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="25071-131">Element</span></span>|<span data-ttu-id="25071-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="25071-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25071-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="25071-133">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="25071-134">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="25071-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="25071-135">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="25071-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25071-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25071-136">Remarks</span></span>

<span data-ttu-id="25071-137">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="25071-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="25071-138">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="25071-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="25071-139">Puede usar los [ \<argumentos >](../windows-workflow-foundation/arguments.md), [ \<Estados >](../windows-workflow-foundation/states.md) y [ \<Estados >](../windows-workflow-foundation/states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y `Closed` argumentos cuando se emite el registro de seguimiento de la actividad.</span><span class="sxs-lookup"><span data-stu-id="25071-139">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="25071-140">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](../windows-workflow-foundation/activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="25071-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="25071-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="25071-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="25071-142">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="25071-142">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="25071-143">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="25071-143">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
