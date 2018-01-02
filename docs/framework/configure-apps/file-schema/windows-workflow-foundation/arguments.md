---
title: '&lt;argumentos&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f233c7fc7d7edd020a750938a45351bb028524d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltargumentsgt"></a><span data-ttu-id="46b11-102">&lt;argumentos&gt;</span><span class="sxs-lookup"><span data-stu-id="46b11-102">&lt;arguments&gt;</span></span>
<span data-ttu-id="46b11-103">Representa una recopilación de argumentos asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="46b11-103">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="46b11-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="46b11-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="46b11-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="46b11-105">\<system.serviceModel></span></span>  
<span data-ttu-id="46b11-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="46b11-106">\<tracking></span></span>  
<span data-ttu-id="46b11-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="46b11-107">\<trackingProfile></span></span>  
<span data-ttu-id="46b11-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="46b11-108">\<workflow></span></span>  
<span data-ttu-id="46b11-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="46b11-109">\<activityStateQueries></span></span>  
<span data-ttu-id="46b11-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="46b11-110">\<activityStateQuery></span></span>  
<span data-ttu-id="46b11-111">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="46b11-111">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b11-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46b11-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46b11-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46b11-113">Attributes and Elements</span></span>  
 <span data-ttu-id="46b11-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46b11-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46b11-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="46b11-115">Attributes</span></span>  
 <span data-ttu-id="46b11-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46b11-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46b11-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="46b11-117">Child Elements</span></span>  
  
|<span data-ttu-id="46b11-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="46b11-118">Element</span></span>|<span data-ttu-id="46b11-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="46b11-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46b11-120">\<argumento ></span><span class="sxs-lookup"><span data-stu-id="46b11-120">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="46b11-121">Un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="46b11-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46b11-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="46b11-122">Parent Elements</span></span>  
  
|<span data-ttu-id="46b11-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="46b11-123">Element</span></span>|<span data-ttu-id="46b11-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="46b11-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46b11-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="46b11-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="46b11-126">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="46b11-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="46b11-127">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="46b11-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46b11-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46b11-128">Remarks</span></span>  
 <span data-ttu-id="46b11-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="46b11-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="46b11-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="46b11-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="46b11-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="46b11-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="46b11-132">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="46b11-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46b11-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="46b11-133">See Also</span></span>  
 <span data-ttu-id="46b11-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46b11-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="46b11-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="46b11-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="46b11-136">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="46b11-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="46b11-137">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="46b11-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
