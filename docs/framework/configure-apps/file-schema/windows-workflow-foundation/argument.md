---
title: '&lt;Argumento&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: bfcb98085e0b2292d46acfd0a57096219afff606
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756324"
---
# <a name="ltargumentgt"></a><span data-ttu-id="0085c-102">&lt;Argumento&gt;</span><span class="sxs-lookup"><span data-stu-id="0085c-102">&lt;argument&gt;</span></span>
<span data-ttu-id="0085c-103">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="0085c-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="0085c-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0085c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0085c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="0085c-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="0085c-106">\<tracking></span></span>  
<span data-ttu-id="0085c-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0085c-107">\<trackingProfile></span></span>  
<span data-ttu-id="0085c-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="0085c-108">\<workflow></span></span>  
<span data-ttu-id="0085c-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="0085c-109">\<activityStateQueries></span></span>  
<span data-ttu-id="0085c-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="0085c-110">\<activityStateQuery></span></span>  
<span data-ttu-id="0085c-111">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="0085c-111">\<arguments></span></span>  
<span data-ttu-id="0085c-112">\<argumento ></span><span class="sxs-lookup"><span data-stu-id="0085c-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0085c-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0085c-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0085c-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0085c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="0085c-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0085c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0085c-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="0085c-116">Attributes</span></span>  
  
|<span data-ttu-id="0085c-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="0085c-117">Attribute</span></span>|<span data-ttu-id="0085c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="0085c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0085c-119">name</span><span class="sxs-lookup"><span data-stu-id="0085c-119">name</span></span>|<span data-ttu-id="0085c-120">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="0085c-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0085c-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0085c-121">Child Elements</span></span>  
 <span data-ttu-id="0085c-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0085c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0085c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0085c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="0085c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="0085c-124">Element</span></span>|<span data-ttu-id="0085c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="0085c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0085c-126">\<argumentos ></span><span class="sxs-lookup"><span data-stu-id="0085c-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="0085c-127">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="0085c-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0085c-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0085c-128">Remarks</span></span>  
 <span data-ttu-id="0085c-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0085c-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="0085c-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="0085c-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="0085c-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0085c-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="0085c-132">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="0085c-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0085c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="0085c-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0085c-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0085c-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0085c-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0085c-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
