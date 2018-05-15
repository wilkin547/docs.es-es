---
title: '&lt;Variable&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 7d41d80bfe83cfafca01509d50709e21730bcb97
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltvariablegt"></a><span data-ttu-id="fc89f-102">&lt;Variable&gt;</span><span class="sxs-lookup"><span data-stu-id="fc89f-102">&lt;variable&gt;</span></span>
<span data-ttu-id="fc89f-103">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="fc89f-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="fc89f-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="fc89f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fc89f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fc89f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="fc89f-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="fc89f-106">\<tracking></span></span>  
<span data-ttu-id="fc89f-107">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="fc89f-107">\<profiles></span></span>  
<span data-ttu-id="fc89f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="fc89f-108">\<trackingProfile></span></span>  
<span data-ttu-id="fc89f-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="fc89f-109">\<workflow></span></span>  
<span data-ttu-id="fc89f-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="fc89f-110">\<activityStateQueries></span></span>  
<span data-ttu-id="fc89f-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="fc89f-111">\<activityStateQuery></span></span>  
<span data-ttu-id="fc89f-112">\<las variables ></span><span class="sxs-lookup"><span data-stu-id="fc89f-112">\<variables></span></span>  
<span data-ttu-id="fc89f-113">\<variable ></span><span class="sxs-lookup"><span data-stu-id="fc89f-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc89f-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc89f-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc89f-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc89f-115">Attributes and Elements</span></span>  
 <span data-ttu-id="fc89f-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc89f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc89f-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc89f-117">Attributes</span></span>  
  
|<span data-ttu-id="fc89f-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc89f-118">Attribute</span></span>|<span data-ttu-id="fc89f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc89f-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc89f-120">name</span><span class="sxs-lookup"><span data-stu-id="fc89f-120">name</span></span>|<span data-ttu-id="fc89f-121">Una cadena que especifica el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="fc89f-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc89f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc89f-122">Child Elements</span></span>  
 <span data-ttu-id="fc89f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fc89f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc89f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc89f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fc89f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc89f-125">Element</span></span>|<span data-ttu-id="fc89f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc89f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc89f-127">\<variable ></span><span class="sxs-lookup"><span data-stu-id="fc89f-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="fc89f-128">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="fc89f-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc89f-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc89f-129">Remarks</span></span>  
 <span data-ttu-id="fc89f-130">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fc89f-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="fc89f-131">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="fc89f-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="fc89f-132">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc89f-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="fc89f-133">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="fc89f-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc89f-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc89f-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="fc89f-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="fc89f-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="fc89f-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fc89f-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
