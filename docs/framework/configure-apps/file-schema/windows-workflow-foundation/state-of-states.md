---
title: <state> de <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 7c7326b2fd5ae39ca4c0f39fac05444802fa3d49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947493"
---
# <a name="state-of-states"></a><span data-ttu-id="ed454-102">\<estado > de \<Estados ></span><span class="sxs-lookup"><span data-stu-id="ed454-102">\<state> of \<states></span></span>
<span data-ttu-id="ed454-103">Un elemento de configuración que contiene el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ed454-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="ed454-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ed454-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ed454-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ed454-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ed454-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ed454-106">\<tracking></span></span>  
<span data-ttu-id="ed454-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ed454-107">\<trackingProfile></span></span>  
<span data-ttu-id="ed454-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ed454-108">\<workflow></span></span>  
<span data-ttu-id="ed454-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ed454-109">\<activityStateQueries></span></span>  
<span data-ttu-id="ed454-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ed454-110">\<activityStateQuery></span></span>  
<span data-ttu-id="ed454-111">\<states></span><span class="sxs-lookup"><span data-stu-id="ed454-111">\<states></span></span>  
<span data-ttu-id="ed454-112">\<> de estado</span><span class="sxs-lookup"><span data-stu-id="ed454-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed454-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed454-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ed454-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ed454-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ed454-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ed454-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ed454-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ed454-116">Attributes</span></span>  
  
|<span data-ttu-id="ed454-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="ed454-117">Attribute</span></span>|<span data-ttu-id="ed454-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ed454-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ed454-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="ed454-119">name</span></span>|<span data-ttu-id="ed454-120">Una cadena que especifica el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ed454-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ed454-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ed454-121">Child Elements</span></span>  
 <span data-ttu-id="ed454-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ed454-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ed454-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ed454-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ed454-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ed454-124">Element</span></span>|<span data-ttu-id="ed454-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ed454-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ed454-126">\<states></span><span class="sxs-lookup"><span data-stu-id="ed454-126">\<states></span></span>](states-of-activitystatequery.md)|<span data-ttu-id="ed454-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ed454-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed454-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed454-128">Remarks</span></span>  
 <span data-ttu-id="ed454-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ed454-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ed454-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="ed454-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ed454-131">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ed454-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ed454-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="ed454-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ed454-133">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="ed454-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ed454-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed454-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ed454-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ed454-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ed454-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ed454-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
