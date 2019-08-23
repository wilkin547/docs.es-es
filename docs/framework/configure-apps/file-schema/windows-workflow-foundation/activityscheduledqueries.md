---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 89de9ef10449fbae78a8c5b558101a2cf6477b07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945533"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="2888a-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2888a-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="2888a-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2888a-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2888a-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="2888a-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="2888a-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="2888a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2888a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2888a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2888a-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2888a-106">\<tracking></span></span>  
<span data-ttu-id="2888a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2888a-107">\<trackingProfile></span></span>  
<span data-ttu-id="2888a-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2888a-108">\<workflow></span></span>  
<span data-ttu-id="2888a-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2888a-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2888a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2888a-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2888a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2888a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2888a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2888a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2888a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2888a-113">Attributes</span></span>  
 <span data-ttu-id="2888a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2888a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2888a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2888a-115">Child Elements</span></span>  
  
|<span data-ttu-id="2888a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2888a-116">Element</span></span>|<span data-ttu-id="2888a-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2888a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2888a-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2888a-118">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="2888a-119">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2888a-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2888a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2888a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2888a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2888a-121">Element</span></span>|<span data-ttu-id="2888a-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2888a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2888a-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2888a-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="2888a-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="2888a-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2888a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2888a-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2888a-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2888a-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2888a-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2888a-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
