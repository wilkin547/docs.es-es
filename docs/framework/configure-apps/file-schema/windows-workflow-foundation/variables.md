---
title: '&lt;variables&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: d0dc83951bdf894d0061971ae4b79854a7c8bcd8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltvariablesgt"></a><span data-ttu-id="62bb0-102">&lt;variables&gt;</span><span class="sxs-lookup"><span data-stu-id="62bb0-102">&lt;variables&gt;</span></span>
<span data-ttu-id="62bb0-103">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="62bb0-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="62bb0-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="62bb0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="62bb0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62bb0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="62bb0-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="62bb0-106">\<tracking></span></span>  
<span data-ttu-id="62bb0-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="62bb0-107">\<trackingProfile></span></span>  
<span data-ttu-id="62bb0-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="62bb0-108">\<workflow></span></span>  
<span data-ttu-id="62bb0-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="62bb0-109">\<activityStateQueries></span></span>  
<span data-ttu-id="62bb0-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="62bb0-110">\<activityStateQuery></span></span>  
<span data-ttu-id="62bb0-111">\<las variables ></span><span class="sxs-lookup"><span data-stu-id="62bb0-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62bb0-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="62bb0-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62bb0-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="62bb0-113">Attributes and Elements</span></span>  
 <span data-ttu-id="62bb0-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="62bb0-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62bb0-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="62bb0-115">Attributes</span></span>  
 <span data-ttu-id="62bb0-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="62bb0-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62bb0-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="62bb0-117">Child Elements</span></span>  
  
|<span data-ttu-id="62bb0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="62bb0-118">Element</span></span>|<span data-ttu-id="62bb0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="62bb0-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62bb0-120">\<variable ></span><span class="sxs-lookup"><span data-stu-id="62bb0-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="62bb0-121">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="62bb0-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62bb0-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="62bb0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="62bb0-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="62bb0-123">Element</span></span>|<span data-ttu-id="62bb0-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="62bb0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62bb0-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="62bb0-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="62bb0-126">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="62bb0-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="62bb0-127">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="62bb0-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62bb0-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62bb0-128">Remarks</span></span>  
 <span data-ttu-id="62bb0-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="62bb0-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="62bb0-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="62bb0-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="62bb0-131">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elementos que se va a extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el ejemplo siguiente se muestra una consulta de estado de actividad que extrae variables y argumentos cuando la actividad `Closed` se genera un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="62bb0-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="62bb0-132">Las variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben en un seguimiento perfil usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="62bb0-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="62bb0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="62bb0-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="62bb0-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="62bb0-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="62bb0-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="62bb0-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
