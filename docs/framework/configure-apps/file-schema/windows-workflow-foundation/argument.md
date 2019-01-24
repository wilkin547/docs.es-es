---
title: '&lt;argument&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 3744781f844d4a1728ba1e9846b2b8c56c0ad8fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554613"
---
# <a name="ltargumentgt"></a><span data-ttu-id="c6d8c-102">&lt;argument&gt;</span><span class="sxs-lookup"><span data-stu-id="c6d8c-102">&lt;argument&gt;</span></span>
<span data-ttu-id="c6d8c-103">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-103">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="c6d8c-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c6d8c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c6d8c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c6d8c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c6d8c-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c6d8c-106">\<tracking></span></span>  
<span data-ttu-id="c6d8c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c6d8c-107">\<trackingProfile></span></span>  
<span data-ttu-id="c6d8c-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="c6d8c-108">\<workflow></span></span>  
<span data-ttu-id="c6d8c-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="c6d8c-109">\<activityStateQueries></span></span>  
<span data-ttu-id="c6d8c-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="c6d8c-110">\<activityStateQuery></span></span>  
<span data-ttu-id="c6d8c-111">\<arguments></span><span class="sxs-lookup"><span data-stu-id="c6d8c-111">\<arguments></span></span>  
<span data-ttu-id="c6d8c-112">\<argument></span><span class="sxs-lookup"><span data-stu-id="c6d8c-112">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d8c-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6d8c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6d8c-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c6d8c-114">Attributes and Elements</span></span>  
 <span data-ttu-id="c6d8c-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6d8c-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="c6d8c-116">Attributes</span></span>  
  
|<span data-ttu-id="c6d8c-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="c6d8c-117">Attribute</span></span>|<span data-ttu-id="c6d8c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6d8c-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6d8c-119">name</span><span class="sxs-lookup"><span data-stu-id="c6d8c-119">name</span></span>|<span data-ttu-id="c6d8c-120">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6d8c-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c6d8c-121">Child Elements</span></span>  
 <span data-ttu-id="c6d8c-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6d8c-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c6d8c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c6d8c-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c6d8c-124">Element</span></span>|<span data-ttu-id="c6d8c-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6d8c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6d8c-126">\<arguments></span><span class="sxs-lookup"><span data-stu-id="c6d8c-126">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="c6d8c-127">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6d8c-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c6d8c-128">Remarks</span></span>  
 <span data-ttu-id="c6d8c-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="c6d8c-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="c6d8c-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="c6d8c-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="c6d8c-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c6d8c-133">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="c6d8c-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c6d8c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d8c-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c6d8c-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c6d8c-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c6d8c-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c6d8c-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
