---
title: <activityStateQuery>de WCF
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70991214"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="119bb-102">\<activityStateQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="119bb-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="119bb-103">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119bb-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="119bb-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119bb-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="119bb-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="119bb-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="119bb-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="119bb-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="119bb-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="119bb-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="119bb-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="119bb-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="119bb-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="119bb-109">Attributes and elements</span></span>  

<span data-ttu-id="119bb-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="119bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="119bb-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="119bb-111">Attributes</span></span>  
  
|<span data-ttu-id="119bb-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="119bb-112">Attribute</span></span>|<span data-ttu-id="119bb-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="119bb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="119bb-114">activityName</span><span class="sxs-lookup"><span data-stu-id="119bb-114">activityName</span></span>|<span data-ttu-id="119bb-115">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="119bb-115">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="119bb-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="119bb-116">Child elements</span></span>  
  
|<span data-ttu-id="119bb-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="119bb-117">Element</span></span>|<span data-ttu-id="119bb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="119bb-118">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="119bb-119">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="119bb-119">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="119bb-120">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="119bb-120">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](../windows-workflow-foundation/states.md)|<span data-ttu-id="119bb-121">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="119bb-121">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="119bb-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="119bb-122">Parent elements</span></span>  
  
|<span data-ttu-id="119bb-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="119bb-123">Element</span></span>|<span data-ttu-id="119bb-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="119bb-124">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="119bb-125">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="119bb-125">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="119bb-126">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="119bb-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="119bb-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="119bb-127">Remarks</span></span>

<span data-ttu-id="119bb-128">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119bb-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="119bb-129">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="119bb-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="119bb-130">Puede usar los [\<arguments>](../windows-workflow-foundation/arguments.md) elementos, [\<states>](../windows-workflow-foundation/states.md) y [\<states>](../windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="119bb-130">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="119bb-131">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="119bb-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="119bb-132">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="119bb-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="119bb-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="119bb-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="119bb-134">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="119bb-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="119bb-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="119bb-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
