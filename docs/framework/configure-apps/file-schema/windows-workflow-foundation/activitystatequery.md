---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: fdb173f6d16087e921fc7f2edbb30fa901545eac
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177766"
---
# \<activityStateQuery>

<span data-ttu-id="0ad36-101">Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ad36-101">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="0ad36-102">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ad36-102">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="0ad36-103">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="0ad36-103">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="0ad36-104">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="0ad36-104">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="0ad36-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0ad36-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="0ad36-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ad36-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ad36-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0ad36-107">Attributes and Elements</span></span>  

 <span data-ttu-id="0ad36-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0ad36-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ad36-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="0ad36-109">Attributes</span></span>  
  
|<span data-ttu-id="0ad36-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="0ad36-110">Attribute</span></span>|<span data-ttu-id="0ad36-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad36-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ad36-112">activityName</span><span class="sxs-lookup"><span data-stu-id="0ad36-112">activityName</span></span>|<span data-ttu-id="0ad36-113">Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="0ad36-113">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ad36-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0ad36-114">Child Elements</span></span>  
  
|<span data-ttu-id="0ad36-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ad36-115">Element</span></span>|<span data-ttu-id="0ad36-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad36-116">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="0ad36-117">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="0ad36-117">A collection of arguments associated with this activity query.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="0ad36-118">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0ad36-118">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[\<states>](states.md)|<span data-ttu-id="0ad36-119">Una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="0ad36-119">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ad36-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0ad36-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0ad36-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0ad36-121">Element</span></span>|<span data-ttu-id="0ad36-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad36-122">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="0ad36-123">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="0ad36-123">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0ad36-124">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="0ad36-124">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad36-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0ad36-125">Remarks</span></span>  

 <span data-ttu-id="0ad36-126">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ad36-126">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0ad36-127">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0ad36-127">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0ad36-128">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ad36-128">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="0ad36-129">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="0ad36-129">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0ad36-130">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="0ad36-130">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0ad36-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ad36-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0ad36-132">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0ad36-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0ad36-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0ad36-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
