---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398899"
---
# \<argument>
<span data-ttu-id="d729c-101">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="d729c-101">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="d729c-102">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d729c-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="d729c-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d729c-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d729c-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d729c-104">Attributes and Elements</span></span>  
 <span data-ttu-id="d729c-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d729c-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d729c-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="d729c-106">Attributes</span></span>  
  
|<span data-ttu-id="d729c-107">Atributo</span><span class="sxs-lookup"><span data-stu-id="d729c-107">Attribute</span></span>|<span data-ttu-id="d729c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d729c-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d729c-109">name</span><span class="sxs-lookup"><span data-stu-id="d729c-109">name</span></span>|<span data-ttu-id="d729c-110">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="d729c-110">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d729c-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d729c-111">Child Elements</span></span>  
 <span data-ttu-id="d729c-112">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d729c-112">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d729c-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d729c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="d729c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="d729c-114">Element</span></span>|<span data-ttu-id="d729c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d729c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="d729c-116">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="d729c-116">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d729c-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d729c-117">Remarks</span></span>  
 <span data-ttu-id="d729c-118">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d729c-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="d729c-119">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="d729c-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="d729c-120">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d729c-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="d729c-121">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="d729c-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="d729c-122">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="d729c-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d729c-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d729c-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d729c-124">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d729c-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d729c-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d729c-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
