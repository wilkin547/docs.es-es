---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: e386ad261422904d3f33385bb80bdb8c1ac029b9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267972"
---
# <a name="argument"></a><span data-ttu-id="845b8-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="845b8-101">\<argument></span></span>
<span data-ttu-id="845b8-102">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="845b8-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="845b8-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="845b8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="845b8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="845b8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="845b8-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="845b8-105">\<tracking></span></span>  
<span data-ttu-id="845b8-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="845b8-106">\<trackingProfile></span></span>  
<span data-ttu-id="845b8-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="845b8-107">\<workflow></span></span>  
<span data-ttu-id="845b8-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="845b8-108">\<activityStateQueries></span></span>  
<span data-ttu-id="845b8-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="845b8-109">\<activityStateQuery></span></span>  
<span data-ttu-id="845b8-110">\<arguments></span><span class="sxs-lookup"><span data-stu-id="845b8-110">\<arguments></span></span>  
<span data-ttu-id="845b8-111">\<argument></span><span class="sxs-lookup"><span data-stu-id="845b8-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="845b8-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="845b8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="845b8-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="845b8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="845b8-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="845b8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="845b8-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="845b8-115">Attributes</span></span>  
  
|<span data-ttu-id="845b8-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="845b8-116">Attribute</span></span>|<span data-ttu-id="845b8-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="845b8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="845b8-118">name</span><span class="sxs-lookup"><span data-stu-id="845b8-118">name</span></span>|<span data-ttu-id="845b8-119">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="845b8-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="845b8-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="845b8-120">Child Elements</span></span>  
 <span data-ttu-id="845b8-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="845b8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="845b8-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="845b8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="845b8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="845b8-123">Element</span></span>|<span data-ttu-id="845b8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="845b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="845b8-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="845b8-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="845b8-126">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="845b8-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="845b8-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="845b8-127">Remarks</span></span>  
 <span data-ttu-id="845b8-128">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="845b8-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="845b8-129">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="845b8-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="845b8-130">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="845b8-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="845b8-131">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="845b8-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="845b8-132">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="845b8-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="845b8-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="845b8-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="845b8-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="845b8-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="845b8-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="845b8-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
