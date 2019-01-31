---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: e6891144d613623b199e7279aa091d4d7cbe4445
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284562"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="2e59a-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2e59a-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="2e59a-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2e59a-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2e59a-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="2e59a-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="2e59a-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2e59a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2e59a-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2e59a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2e59a-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2e59a-106">\<tracking></span></span>  
<span data-ttu-id="2e59a-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2e59a-107">\<trackingProfile></span></span>  
<span data-ttu-id="2e59a-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="2e59a-108">\<workflow></span></span>  
<span data-ttu-id="2e59a-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2e59a-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e59a-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e59a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e59a-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2e59a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2e59a-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2e59a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e59a-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="2e59a-113">Attributes</span></span>  
 <span data-ttu-id="2e59a-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2e59a-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2e59a-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2e59a-115">Child Elements</span></span>  
  
|<span data-ttu-id="2e59a-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e59a-116">Element</span></span>|<span data-ttu-id="2e59a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e59a-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e59a-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2e59a-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="2e59a-119">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2e59a-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e59a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2e59a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2e59a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2e59a-121">Element</span></span>|<span data-ttu-id="2e59a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e59a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e59a-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2e59a-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2e59a-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2e59a-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e59a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e59a-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2e59a-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2e59a-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2e59a-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2e59a-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
