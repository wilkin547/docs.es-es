---
description: 'Más información sobre: <state> de <states>'
title: <state> de <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 748044986143f182faa0edafb0cfe299a79a704e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781992"
---
# <a name="state-of-states"></a><span data-ttu-id="dabd2-103">\<state> de \<states></span><span class="sxs-lookup"><span data-stu-id="dabd2-103">\<state> of \<states></span></span>

<span data-ttu-id="dabd2-104">Un elemento de configuración que contiene el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dabd2-104">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="dabd2-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dabd2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**  
  
## <a name="syntax"></a><span data-ttu-id="dabd2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dabd2-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dabd2-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dabd2-107">Attributes and Elements</span></span>  

 <span data-ttu-id="dabd2-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dabd2-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dabd2-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="dabd2-109">Attributes</span></span>  
  
|<span data-ttu-id="dabd2-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="dabd2-110">Attribute</span></span>|<span data-ttu-id="dabd2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="dabd2-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dabd2-112">name</span><span class="sxs-lookup"><span data-stu-id="dabd2-112">name</span></span>|<span data-ttu-id="dabd2-113">Una cadena que especifica el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dabd2-113">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dabd2-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dabd2-114">Child Elements</span></span>  

 <span data-ttu-id="dabd2-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dabd2-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dabd2-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dabd2-116">Parent Elements</span></span>  
  
|<span data-ttu-id="dabd2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dabd2-117">Element</span></span>|<span data-ttu-id="dabd2-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="dabd2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states-of-activitystatequery.md)|<span data-ttu-id="dabd2-119">Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dabd2-119">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dabd2-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dabd2-120">Remarks</span></span>  

 <span data-ttu-id="dabd2-121">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dabd2-121">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="dabd2-122">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="dabd2-122">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="dabd2-123">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dabd2-123">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="dabd2-124">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="dabd2-124">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="dabd2-125">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="dabd2-125">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dabd2-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="dabd2-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dabd2-127">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dabd2-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dabd2-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dabd2-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
