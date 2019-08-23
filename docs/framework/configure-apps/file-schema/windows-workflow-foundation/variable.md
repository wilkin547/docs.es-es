---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947274"
---
# <a name="variable"></a><span data-ttu-id="640e4-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="640e4-101">\<variable></span></span>
<span data-ttu-id="640e4-102">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="640e4-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="640e4-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="640e4-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="640e4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="640e4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="640e4-105">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="640e4-105">\<tracking></span></span>  
<span data-ttu-id="640e4-106">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="640e4-106">\<profiles></span></span>  
<span data-ttu-id="640e4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="640e4-107">\<trackingProfile></span></span>  
<span data-ttu-id="640e4-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="640e4-108">\<workflow></span></span>  
<span data-ttu-id="640e4-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="640e4-109">\<activityStateQueries></span></span>  
<span data-ttu-id="640e4-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="640e4-110">\<activityStateQuery></span></span>  
<span data-ttu-id="640e4-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="640e4-111">\<variables></span></span>  
<span data-ttu-id="640e4-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="640e4-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="640e4-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="640e4-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="640e4-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="640e4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="640e4-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="640e4-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="640e4-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="640e4-116">Attributes</span></span>  
  
|<span data-ttu-id="640e4-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="640e4-117">Attribute</span></span>|<span data-ttu-id="640e4-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="640e4-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="640e4-119">name</span><span class="sxs-lookup"><span data-stu-id="640e4-119">name</span></span>|<span data-ttu-id="640e4-120">Una cadena que especifica el nombre de la variable.</span><span class="sxs-lookup"><span data-stu-id="640e4-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="640e4-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="640e4-121">Child Elements</span></span>  
 <span data-ttu-id="640e4-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="640e4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="640e4-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="640e4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="640e4-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="640e4-124">Element</span></span>|<span data-ttu-id="640e4-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="640e4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="640e4-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="640e4-126">\<variable></span></span>](variable.md)|<span data-ttu-id="640e4-127">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="640e4-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="640e4-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="640e4-128">Remarks</span></span>  
 <span data-ttu-id="640e4-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="640e4-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="640e4-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="640e4-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="640e4-131">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="640e4-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="640e4-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="640e4-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="640e4-133">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="640e4-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="640e4-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="640e4-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="640e4-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="640e4-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="640e4-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="640e4-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
