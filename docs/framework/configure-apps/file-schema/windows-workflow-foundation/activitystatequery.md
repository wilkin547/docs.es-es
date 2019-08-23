---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945430"
---
# <a name="activitystatequery"></a><span data-ttu-id="ef2b3-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ef2b3-101">\<activityStateQuery></span></span>
<span data-ttu-id="ef2b3-102">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="ef2b3-103">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="ef2b3-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="ef2b3-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="ef2b3-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ef2b3-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ef2b3-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ef2b3-107">\<system.serviceModel></span></span>  
<span data-ttu-id="ef2b3-108">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ef2b3-108">\<tracking></span></span>  
<span data-ttu-id="ef2b3-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ef2b3-109">\<trackingProfile></span></span>  
<span data-ttu-id="ef2b3-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef2b3-110">\<workflow></span></span>  
<span data-ttu-id="ef2b3-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ef2b3-111">\<activityStateQueries></span></span>  
<span data-ttu-id="ef2b3-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ef2b3-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef2b3-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef2b3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef2b3-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef2b3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ef2b3-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef2b3-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef2b3-116">Attributes</span></span>  
  
|<span data-ttu-id="ef2b3-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="ef2b3-117">Attribute</span></span>|<span data-ttu-id="ef2b3-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef2b3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef2b3-119">activityName</span><span class="sxs-lookup"><span data-stu-id="ef2b3-119">activityName</span></span>|<span data-ttu-id="ef2b3-120">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef2b3-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef2b3-121">Child Elements</span></span>  
  
|<span data-ttu-id="ef2b3-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef2b3-122">Element</span></span>|<span data-ttu-id="ef2b3-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef2b3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef2b3-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="ef2b3-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="ef2b3-125">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="ef2b3-126">\<states></span><span class="sxs-lookup"><span data-stu-id="ef2b3-126">\<states></span></span>](states.md)|<span data-ttu-id="ef2b3-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="ef2b3-128">\<states></span><span class="sxs-lookup"><span data-stu-id="ef2b3-128">\<states></span></span>](states.md)|<span data-ttu-id="ef2b3-129">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef2b3-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef2b3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="ef2b3-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef2b3-131">Element</span></span>|<span data-ttu-id="ef2b3-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef2b3-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef2b3-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="ef2b3-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="ef2b3-134">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ef2b3-135">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef2b3-136">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef2b3-136">Remarks</span></span>  
 <span data-ttu-id="ef2b3-137">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ef2b3-138">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ef2b3-139">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ef2b3-140">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ef2b3-141">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="ef2b3-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ef2b3-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef2b3-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef2b3-143">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef2b3-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef2b3-144">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ef2b3-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
