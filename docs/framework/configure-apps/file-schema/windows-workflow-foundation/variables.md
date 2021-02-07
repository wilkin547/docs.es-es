---
description: 'Más información acerca de: <variables>'
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: e77c4fb1d4d16a655cd1918bb9460177b7ff3266
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698016"
---
# \<variables>

<span data-ttu-id="00471-102">Representa una colección de variables asociada a esta consulta de actividad.</span><span class="sxs-lookup"><span data-stu-id="00471-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="00471-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="00471-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<variables>**  
  
## <a name="syntax"></a><span data-ttu-id="00471-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00471-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00471-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00471-105">Attributes and Elements</span></span>  

 <span data-ttu-id="00471-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00471-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00471-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="00471-107">Attributes</span></span>  

 <span data-ttu-id="00471-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00471-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00471-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00471-109">Child Elements</span></span>  
  
|<span data-ttu-id="00471-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="00471-110">Element</span></span>|<span data-ttu-id="00471-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="00471-111">Description</span></span>|  
|-------------|-----------------|  
|[\<variable>](variable.md)|<span data-ttu-id="00471-112">Una variable asociada a una consulta de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="00471-112">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00471-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00471-113">Parent Elements</span></span>  
  
|<span data-ttu-id="00471-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="00471-114">Element</span></span>|<span data-ttu-id="00471-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="00471-115">Description</span></span>|  
|-------------|-----------------|  
|[\<activityStateQuery>](activitystatequery.md)|<span data-ttu-id="00471-116">Representa un elemento de configuración que se utiliza para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="00471-116">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="00471-117">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="00471-117">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00471-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="00471-118">Remarks</span></span>  

 <span data-ttu-id="00471-119">Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="00471-119">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="00471-120">Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.</span><span class="sxs-lookup"><span data-stu-id="00471-120">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="00471-121">Puede usar los [\<arguments>](arguments.md) elementos, [\<states>](states.md) y [\<states>](states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="00471-121">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="00471-122">El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.</span><span class="sxs-lookup"><span data-stu-id="00471-122">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="00471-123">Las variables y los argumentos solo se pueden extraer con un ActivityStateRecord y, por tanto, se suscriben a dentro de un perfil de seguimiento mediante [\<activityStateQuery>](activitystatequery.md) .</span><span class="sxs-lookup"><span data-stu-id="00471-123">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="00471-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="00471-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00471-125">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="00471-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00471-126">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="00471-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
