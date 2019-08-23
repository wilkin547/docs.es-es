---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: bb7ae702209df3c0297ec2cfac6b09ee47ad9558
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946127"
---
# <a name="arguments"></a><span data-ttu-id="1dacf-101">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="1dacf-101">\<arguments></span></span>
<span data-ttu-id="1dacf-102">Representa una recopilación de argumentos asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="1dacf-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="1dacf-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1dacf-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1dacf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1dacf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1dacf-105">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1dacf-105">\<tracking></span></span>  
<span data-ttu-id="1dacf-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1dacf-106">\<trackingProfile></span></span>  
<span data-ttu-id="1dacf-107">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1dacf-107">\<workflow></span></span>  
<span data-ttu-id="1dacf-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="1dacf-108">\<activityStateQueries></span></span>  
<span data-ttu-id="1dacf-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="1dacf-109">\<activityStateQuery></span></span>  
<span data-ttu-id="1dacf-110">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="1dacf-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1dacf-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dacf-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1dacf-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1dacf-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1dacf-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1dacf-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1dacf-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="1dacf-114">Attributes</span></span>  
 <span data-ttu-id="1dacf-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1dacf-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1dacf-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1dacf-116">Child Elements</span></span>  
  
|<span data-ttu-id="1dacf-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dacf-117">Element</span></span>|<span data-ttu-id="1dacf-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1dacf-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dacf-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="1dacf-119">\<argument></span></span>](argument.md)|<span data-ttu-id="1dacf-120">Un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="1dacf-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1dacf-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1dacf-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1dacf-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="1dacf-122">Element</span></span>|<span data-ttu-id="1dacf-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1dacf-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1dacf-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="1dacf-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="1dacf-125">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="1dacf-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="1dacf-126">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="1dacf-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1dacf-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dacf-127">Remarks</span></span>  
 <span data-ttu-id="1dacf-128">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1dacf-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="1dacf-129">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1dacf-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="1dacf-130">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1dacf-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="1dacf-131">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="1dacf-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="1dacf-132">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="1dacf-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1dacf-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1dacf-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1dacf-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1dacf-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1dacf-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1dacf-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
