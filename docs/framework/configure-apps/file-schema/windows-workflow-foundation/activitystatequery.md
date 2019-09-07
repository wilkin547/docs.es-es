---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 5d3c35589330ab5bed5f89c0dafac006b9e3af55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398937"
---
# <a name="activitystatequery"></a><span data-ttu-id="b6b3a-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b6b3a-101">\<activityStateQuery></span></span>
<span data-ttu-id="b6b3a-102">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b6b3a-103">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b6b3a-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="b6b3a-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="b6b3a-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b6b3a-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b6b3a-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6b3a-108">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b6b3a-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b6b3a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b6b3a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b6b3a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="b6b3a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="b6b3a-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQuery**</span><span class="sxs-lookup"><span data-stu-id="b6b3a-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b3a-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6b3a-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6b3a-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b6b3a-115">Attributes and Elements</span></span>  
 <span data-ttu-id="b6b3a-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6b3a-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="b6b3a-117">Attributes</span></span>  
  
|<span data-ttu-id="b6b3a-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="b6b3a-118">Attribute</span></span>|<span data-ttu-id="b6b3a-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b6b3a-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6b3a-120">activityName</span><span class="sxs-lookup"><span data-stu-id="b6b3a-120">activityName</span></span>|<span data-ttu-id="b6b3a-121">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6b3a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b6b3a-122">Child Elements</span></span>  
  
|<span data-ttu-id="b6b3a-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6b3a-123">Element</span></span>|<span data-ttu-id="b6b3a-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b6b3a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6b3a-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="b6b3a-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="b6b3a-126">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="b6b3a-127">\<states></span><span class="sxs-lookup"><span data-stu-id="b6b3a-127">\<states></span></span>](states.md)|<span data-ttu-id="b6b3a-128">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="b6b3a-129">\<states></span><span class="sxs-lookup"><span data-stu-id="b6b3a-129">\<states></span></span>](states.md)|<span data-ttu-id="b6b3a-130">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b6b3a-131">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b6b3a-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b6b3a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="b6b3a-132">Element</span></span>|<span data-ttu-id="b6b3a-133">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b6b3a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6b3a-134">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b6b3a-134">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="b6b3a-135">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b6b3a-136">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6b3a-137">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6b3a-137">Remarks</span></span>  
 <span data-ttu-id="b6b3a-138">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b6b3a-139">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b6b3a-140">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-140">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b6b3a-141">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-141">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b6b3a-142">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="b6b3a-142">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6b3a-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b3a-143">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b6b3a-144">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b6b3a-144">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b6b3a-145">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b6b3a-145">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
