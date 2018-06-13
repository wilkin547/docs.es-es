---
title: '&lt;estado&gt; de &lt;estados&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 8893f6acfc7ec4d6989be2c647b0584093a534a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756857"
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="8ae62-102">&lt;estado&gt; de &lt;estados&gt;</span><span class="sxs-lookup"><span data-stu-id="8ae62-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="8ae62-103">Un elemento de configuración que contiene el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae62-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="8ae62-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="8ae62-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8ae62-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8ae62-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8ae62-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="8ae62-106">\<tracking></span></span>  
<span data-ttu-id="8ae62-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8ae62-107">\<trackingProfile></span></span>  
<span data-ttu-id="8ae62-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="8ae62-108">\<workflow></span></span>  
<span data-ttu-id="8ae62-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8ae62-109">\<activityStateQueries></span></span>  
<span data-ttu-id="8ae62-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8ae62-110">\<activityStateQuery></span></span>  
<span data-ttu-id="8ae62-111">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="8ae62-111">\<states></span></span>  
<span data-ttu-id="8ae62-112">\<estado ></span><span class="sxs-lookup"><span data-stu-id="8ae62-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ae62-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8ae62-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ae62-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8ae62-114">Attributes and Elements</span></span>  
 <span data-ttu-id="8ae62-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8ae62-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ae62-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="8ae62-116">Attributes</span></span>  
  
|<span data-ttu-id="8ae62-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="8ae62-117">Attribute</span></span>|<span data-ttu-id="8ae62-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ae62-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ae62-119">name</span><span class="sxs-lookup"><span data-stu-id="8ae62-119">name</span></span>|<span data-ttu-id="8ae62-120">Una cadena que especifica el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae62-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ae62-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8ae62-121">Child Elements</span></span>  
 <span data-ttu-id="8ae62-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8ae62-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ae62-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8ae62-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8ae62-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8ae62-124">Element</span></span>|<span data-ttu-id="8ae62-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ae62-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ae62-126">\<Estados ></span><span class="sxs-lookup"><span data-stu-id="8ae62-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="8ae62-127">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae62-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ae62-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ae62-128">Remarks</span></span>  
 <span data-ttu-id="8ae62-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8ae62-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8ae62-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ae62-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8ae62-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="8ae62-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8ae62-132">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="8ae62-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8ae62-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ae62-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="8ae62-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="8ae62-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8ae62-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8ae62-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
