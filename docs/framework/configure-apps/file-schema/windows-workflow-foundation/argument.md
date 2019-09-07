---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398899"
---
# <a name="argument"></a><span data-ttu-id="37b29-101">\<argument></span><span class="sxs-lookup"><span data-stu-id="37b29-101">\<argument></span></span>
<span data-ttu-id="37b29-102">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="37b29-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="37b29-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="37b29-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="37b29-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="37b29-105">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="37b29-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="37b29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="37b29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="37b29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQueries**](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="37b29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityStateQuery**](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="37b29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<argumentos >** ](arguments.md)</span><span class="sxs-lookup"><span data-stu-id="37b29-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)</span></span>\
<span data-ttu-id="37b29-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de argumento**</span><span class="sxs-lookup"><span data-stu-id="37b29-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37b29-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37b29-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37b29-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37b29-114">Attributes and Elements</span></span>  
 <span data-ttu-id="37b29-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37b29-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37b29-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="37b29-116">Attributes</span></span>  
  
|<span data-ttu-id="37b29-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="37b29-117">Attribute</span></span>|<span data-ttu-id="37b29-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="37b29-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="37b29-119">name</span><span class="sxs-lookup"><span data-stu-id="37b29-119">name</span></span>|<span data-ttu-id="37b29-120">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="37b29-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="37b29-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37b29-121">Child Elements</span></span>  
 <span data-ttu-id="37b29-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="37b29-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="37b29-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37b29-123">Parent Elements</span></span>  
  
|<span data-ttu-id="37b29-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="37b29-124">Element</span></span>|<span data-ttu-id="37b29-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="37b29-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37b29-126">\<arguments></span><span class="sxs-lookup"><span data-stu-id="37b29-126">\<arguments></span></span>](arguments.md)|<span data-ttu-id="37b29-127">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="37b29-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37b29-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="37b29-128">Remarks</span></span>  
 <span data-ttu-id="37b29-129">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37b29-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="37b29-130">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="37b29-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="37b29-131">Puede usar los [ \<argumentos >](arguments.md), [ \<Estados >](states.md) y [ \<Estados >](states.md) elementos para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37b29-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="37b29-132">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="37b29-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="37b29-133">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por lo tanto, se suscriben [ \<](activitystatequery.md)a dentro de un perfil de seguimiento mediante el > de activityStateQuery.</span><span class="sxs-lookup"><span data-stu-id="37b29-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="37b29-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="37b29-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="37b29-135">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="37b29-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="37b29-136">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="37b29-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
