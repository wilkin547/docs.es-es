---
title: '&lt;variable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad2a4d3768c26755a9437826c70585a43f967d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="1ba43-102">&lt;variable&gt;</span><span class="sxs-lookup"><span data-stu-id="1ba43-102">&lt;variable&gt;</span></span>
<span data-ttu-id="1ba43-103">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="1ba43-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="1ba43-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1ba43-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1ba43-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1ba43-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1ba43-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1ba43-106">\<tracking></span></span>  
<span data-ttu-id="1ba43-107">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="1ba43-107">\<profiles></span></span>  
<span data-ttu-id="1ba43-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1ba43-108">\<trackingProfile></span></span>  
<span data-ttu-id="1ba43-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1ba43-109">\<workflow></span></span>  
<span data-ttu-id="1ba43-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="1ba43-110">\<activityStateQueries></span></span>  
<span data-ttu-id="1ba43-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="1ba43-111">\<activityStateQuery></span></span>  
<span data-ttu-id="1ba43-112">\<las variables ></span><span class="sxs-lookup"><span data-stu-id="1ba43-112">\<variables></span></span>  
<span data-ttu-id="1ba43-113">\<variable ></span><span class="sxs-lookup"><span data-stu-id="1ba43-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba43-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ba43-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ba43-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ba43-115">Attributes and Elements</span></span>  
 <span data-ttu-id="1ba43-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ba43-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ba43-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ba43-117">Attributes</span></span>  
  
|<span data-ttu-id="1ba43-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="1ba43-118">Attribute</span></span>|<span data-ttu-id="1ba43-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ba43-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ba43-120">name</span><span class="sxs-lookup"><span data-stu-id="1ba43-120">name</span></span>|<span data-ttu-id="1ba43-121">Una cadena que especifica el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="1ba43-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ba43-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ba43-122">Child Elements</span></span>  
 <span data-ttu-id="1ba43-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1ba43-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ba43-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ba43-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1ba43-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ba43-125">Element</span></span>|<span data-ttu-id="1ba43-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ba43-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ba43-127">\<variable ></span><span class="sxs-lookup"><span data-stu-id="1ba43-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="1ba43-128">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="1ba43-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba43-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ba43-129">Remarks</span></span>  
 <span data-ttu-id="1ba43-130">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ba43-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="1ba43-131">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="1ba43-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="1ba43-132">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1ba43-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="1ba43-133">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="1ba43-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ba43-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba43-134">See Also</span></span>  
 <span data-ttu-id="1ba43-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1ba43-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1ba43-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1ba43-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1ba43-137">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1ba43-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1ba43-138">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1ba43-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
