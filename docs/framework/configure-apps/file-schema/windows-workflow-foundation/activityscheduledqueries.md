---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 7217fb886cc96e1ad19f96e2c6542277cfc7979e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175765"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="3c7c2-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="3c7c2-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="3c7c2-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3c7c2-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3c7c2-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3c7c2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3c7c2-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c7c2-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3c7c2-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3c7c2-106">\<tracking></span></span>  
<span data-ttu-id="3c7c2-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3c7c2-107">\<trackingProfile></span></span>  
<span data-ttu-id="3c7c2-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3c7c2-108">\<workflow></span></span>  
<span data-ttu-id="3c7c2-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="3c7c2-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c7c2-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c7c2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c7c2-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c7c2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3c7c2-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c7c2-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c7c2-113">Attributes</span></span>  
 <span data-ttu-id="3c7c2-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c7c2-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c7c2-115">Child Elements</span></span>  
  
|<span data-ttu-id="3c7c2-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c7c2-116">Element</span></span>|<span data-ttu-id="3c7c2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c7c2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c7c2-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="3c7c2-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="3c7c2-119">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c7c2-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c7c2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3c7c2-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c7c2-121">Element</span></span>|<span data-ttu-id="3c7c2-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c7c2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c7c2-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3c7c2-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3c7c2-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3c7c2-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3c7c2-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c7c2-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3c7c2-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3c7c2-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3c7c2-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3c7c2-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
