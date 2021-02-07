---
description: 'Más información acerca de: <argument>'
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: 7ef91d78d5d4a56b7291a6443ee7e68fefe4f401
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748874"
---
# \<argument>

<span data-ttu-id="50300-102">Un elemento de configuración que representa un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="50300-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="50300-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="50300-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**  
  
## <a name="syntax"></a><span data-ttu-id="50300-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50300-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50300-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50300-105">Attributes and Elements</span></span>  

 <span data-ttu-id="50300-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50300-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50300-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="50300-107">Attributes</span></span>  
  
|<span data-ttu-id="50300-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="50300-108">Attribute</span></span>|<span data-ttu-id="50300-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="50300-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50300-110">name</span><span class="sxs-lookup"><span data-stu-id="50300-110">name</span></span>|<span data-ttu-id="50300-111">Cadena que especifica el nombre del argumento.</span><span class="sxs-lookup"><span data-stu-id="50300-111">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50300-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50300-112">Child Elements</span></span>  

 <span data-ttu-id="50300-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="50300-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50300-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50300-114">Parent Elements</span></span>  
  
|<span data-ttu-id="50300-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="50300-115">Element</span></span>|<span data-ttu-id="50300-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="50300-116">Description</span></span>|  
|-------------|-----------------|  
|[\<arguments>](arguments.md)|<span data-ttu-id="50300-117">Una colección de argumentos asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="50300-117">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50300-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="50300-118">Remarks</span></span>  

 <span data-ttu-id="50300-119">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="50300-119">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="50300-120">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="50300-120">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="50300-121">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="50300-121">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="50300-122">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="50300-122">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="50300-123">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="50300-123">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="50300-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="50300-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="50300-125">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="50300-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="50300-126">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="50300-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
