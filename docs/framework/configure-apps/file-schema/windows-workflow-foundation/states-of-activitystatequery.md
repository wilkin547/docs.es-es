---
title: <states> de <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947428"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="b7a8f-102">\<indica > de \<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="b7a8f-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="b7a8f-103">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="b7a8f-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b7a8f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b7a8f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b7a8f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b7a8f-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b7a8f-106">\<tracking></span></span>  
<span data-ttu-id="b7a8f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b7a8f-107">\<trackingProfile></span></span>  
<span data-ttu-id="b7a8f-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b7a8f-108">\<workflow></span></span>  
<span data-ttu-id="b7a8f-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b7a8f-109">\<activityStateQueries></span></span>  
<span data-ttu-id="b7a8f-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b7a8f-110">\<activityStateQuery></span></span>  
<span data-ttu-id="b7a8f-111">\<states></span><span class="sxs-lookup"><span data-stu-id="b7a8f-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a8f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7a8f-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7a8f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b7a8f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b7a8f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7a8f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="b7a8f-115">Attributes</span></span>  
 <span data-ttu-id="b7a8f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b7a8f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b7a8f-117">Child Elements</span></span>  
  
|<span data-ttu-id="b7a8f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7a8f-118">Element</span></span>|<span data-ttu-id="b7a8f-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b7a8f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7a8f-120">\<state></span><span class="sxs-lookup"><span data-stu-id="b7a8f-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="b7a8f-121">Un elemento de configuración que contiene los estados de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b7a8f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b7a8f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b7a8f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b7a8f-123">Element</span></span>|<span data-ttu-id="b7a8f-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b7a8f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7a8f-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b7a8f-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="b7a8f-126">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b7a8f-127">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a8f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7a8f-128">Remarks</span></span>  
 <span data-ttu-id="b7a8f-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b7a8f-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b7a8f-131">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b7a8f-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b7a8f-133">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="b7a8f-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7a8f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7a8f-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b7a8f-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b7a8f-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b7a8f-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b7a8f-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
