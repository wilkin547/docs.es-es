---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c85f3c57739c48566c97c8b1debfb7f2c3912bdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196637"
---
# <a name="variable"></a><span data-ttu-id="9c940-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="9c940-101">\<variable></span></span>
<span data-ttu-id="9c940-102">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="9c940-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="9c940-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9c940-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9c940-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9c940-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9c940-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9c940-105">\<tracking></span></span>  
<span data-ttu-id="9c940-106">\<profiles></span><span class="sxs-lookup"><span data-stu-id="9c940-106">\<profiles></span></span>  
<span data-ttu-id="9c940-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9c940-107">\<trackingProfile></span></span>  
<span data-ttu-id="9c940-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9c940-108">\<workflow></span></span>  
<span data-ttu-id="9c940-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="9c940-109">\<activityStateQueries></span></span>  
<span data-ttu-id="9c940-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="9c940-110">\<activityStateQuery></span></span>  
<span data-ttu-id="9c940-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="9c940-111">\<variables></span></span>  
<span data-ttu-id="9c940-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="9c940-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c940-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c940-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c940-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c940-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9c940-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c940-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c940-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c940-116">Attributes</span></span>  
  
|<span data-ttu-id="9c940-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="9c940-117">Attribute</span></span>|<span data-ttu-id="9c940-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c940-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9c940-119">name</span><span class="sxs-lookup"><span data-stu-id="9c940-119">name</span></span>|<span data-ttu-id="9c940-120">Una cadena que especifica el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="9c940-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c940-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c940-121">Child Elements</span></span>  
 <span data-ttu-id="9c940-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9c940-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c940-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c940-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9c940-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c940-124">Element</span></span>|<span data-ttu-id="9c940-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c940-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c940-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="9c940-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="9c940-127">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="9c940-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c940-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c940-128">Remarks</span></span>  
 <span data-ttu-id="9c940-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c940-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="9c940-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c940-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="9c940-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c940-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="9c940-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="9c940-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="9c940-133">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="9c940-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c940-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c940-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9c940-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9c940-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c940-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9c940-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
