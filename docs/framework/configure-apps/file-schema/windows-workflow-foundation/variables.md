---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 3ff568c267331538fb9be0e6cb40eebbca44d882
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276554"
---
# <a name="variables"></a><span data-ttu-id="7705b-101">\<variables></span><span class="sxs-lookup"><span data-stu-id="7705b-101">\<variables></span></span>
<span data-ttu-id="7705b-102">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="7705b-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="7705b-103">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7705b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7705b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7705b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="7705b-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="7705b-105">\<tracking></span></span>  
<span data-ttu-id="7705b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7705b-106">\<trackingProfile></span></span>  
<span data-ttu-id="7705b-107">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="7705b-107">\<workflow></span></span>  
<span data-ttu-id="7705b-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="7705b-108">\<activityStateQueries></span></span>  
<span data-ttu-id="7705b-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="7705b-109">\<activityStateQuery></span></span>  
<span data-ttu-id="7705b-110">\<variables></span><span class="sxs-lookup"><span data-stu-id="7705b-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7705b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7705b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7705b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7705b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7705b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7705b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7705b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7705b-114">Attributes</span></span>  
 <span data-ttu-id="7705b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7705b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7705b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7705b-116">Child Elements</span></span>  
  
|<span data-ttu-id="7705b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="7705b-117">Element</span></span>|<span data-ttu-id="7705b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7705b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7705b-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="7705b-119">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="7705b-120">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="7705b-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7705b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7705b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7705b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="7705b-122">Element</span></span>|<span data-ttu-id="7705b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="7705b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7705b-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="7705b-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="7705b-125">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="7705b-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7705b-126">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="7705b-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7705b-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7705b-127">Remarks</span></span>  
 <span data-ttu-id="7705b-128">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7705b-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="7705b-129">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7705b-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="7705b-130">Puede usar el [ \<argumentos >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [ \<Estados >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7705b-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="7705b-131">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="7705b-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="7705b-132">Variables y argumentos se pueden extraer con ActivityStateRecord y, por tanto, se suscriben dentro de un seguimiento de generar perfiles usando [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span><span class="sxs-lookup"><span data-stu-id="7705b-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7705b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7705b-133">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7705b-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="7705b-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7705b-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7705b-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
