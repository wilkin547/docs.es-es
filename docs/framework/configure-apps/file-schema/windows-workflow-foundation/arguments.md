---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: cb1f96cb6ba2643e28552c354bdd5caf4d43285c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189648"
---
# \<arguments>

<span data-ttu-id="89f40-101">Representa una recopilación de argumentos asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="89f40-101">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="89f40-102">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="89f40-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**  
  
## <a name="syntax"></a><span data-ttu-id="89f40-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89f40-103">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89f40-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="89f40-104">Attributes and Elements</span></span>  

 <span data-ttu-id="89f40-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="89f40-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89f40-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="89f40-106">Attributes</span></span>  

 <span data-ttu-id="89f40-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="89f40-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89f40-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="89f40-108">Child Elements</span></span>  
  
|<span data-ttu-id="89f40-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="89f40-109">Element</span></span>|<span data-ttu-id="89f40-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="89f40-110">Description</span></span>|  
|-------------|-----------------|  
|[\<argument>](argument.md)|<span data-ttu-id="89f40-111">Un argumento asociado a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="89f40-111">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89f40-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="89f40-112">Parent Elements</span></span>  
  
|<span data-ttu-id="89f40-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="89f40-113">Element</span></span>|<span data-ttu-id="89f40-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="89f40-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="89f40-115">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="89f40-115">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="89f40-116">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="89f40-116">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89f40-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89f40-117">Remarks</span></span>  

 <span data-ttu-id="89f40-118">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89f40-118">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="89f40-119">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="89f40-119">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="89f40-120">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89f40-120">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="89f40-121">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="89f40-121">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="89f40-122">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="89f40-122">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89f40-123">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89f40-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="89f40-124">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="89f40-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="89f40-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="89f40-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
