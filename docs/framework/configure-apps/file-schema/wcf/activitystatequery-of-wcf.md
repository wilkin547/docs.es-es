---
title: <activityStateQuery>de WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 233bd3a2fa161222977902cc1053f964e8171173
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850487"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="0c372-102">\<activityStateQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="0c372-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="0c372-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c372-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="0c372-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c372-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="0c372-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="0c372-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="0c372-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="0c372-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="0c372-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0c372-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="0c372-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0c372-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0c372-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="0c372-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="0c372-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="0c372-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="0c372-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="0c372-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="0c372-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="0c372-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityStateQuery**</span><span class="sxs-lookup"><span data-stu-id="0c372-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c372-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c372-116">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c372-117">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0c372-117">Attributes and elements</span></span>  

<span data-ttu-id="0c372-118">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0c372-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c372-119">Atributos</span><span class="sxs-lookup"><span data-stu-id="0c372-119">Attributes</span></span>  
  
|<span data-ttu-id="0c372-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="0c372-120">Attribute</span></span>|<span data-ttu-id="0c372-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c372-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c372-122">activityName</span><span class="sxs-lookup"><span data-stu-id="0c372-122">activityName</span></span>|<span data-ttu-id="0c372-123">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="0c372-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c372-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0c372-124">Child elements</span></span>  
  
|<span data-ttu-id="0c372-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c372-125">Element</span></span>|<span data-ttu-id="0c372-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c372-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c372-127">\<arguments></span><span class="sxs-lookup"><span data-stu-id="0c372-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="0c372-128">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="0c372-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="0c372-129">\<states></span><span class="sxs-lookup"><span data-stu-id="0c372-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="0c372-130">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c372-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="0c372-131">\<states></span><span class="sxs-lookup"><span data-stu-id="0c372-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="0c372-132">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="0c372-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c372-133">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0c372-133">Parent elements</span></span>  
  
|<span data-ttu-id="0c372-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="0c372-134">Element</span></span>|<span data-ttu-id="0c372-135">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0c372-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c372-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="0c372-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0c372-137">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="0c372-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0c372-138">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="0c372-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c372-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c372-139">Remarks</span></span>

<span data-ttu-id="0c372-140">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0c372-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0c372-141">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c372-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0c372-142">Puede usar los [ \<argumentos >](../windows-workflow-foundation/arguments.md), [ \<Estados >](../windows-workflow-foundation/states.md) y [ \<Estados >](../windows-workflow-foundation/states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y `Closed` argumentos cuando se emite el registro de seguimiento de la actividad.</span><span class="sxs-lookup"><span data-stu-id="0c372-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0c372-143">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](../windows-workflow-foundation/activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="0c372-143">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c372-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c372-144">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="0c372-145">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0c372-145">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0c372-146">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0c372-146">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
