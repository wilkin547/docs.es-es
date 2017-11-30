---
title: '&lt;activityScheduledQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 686b58d9efa4420de26fd7be52fe76208af63c6b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="782d8-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="782d8-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="782d8-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="782d8-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="782d8-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="782d8-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="782d8-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="782d8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="782d8-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="782d8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="782d8-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="782d8-107">\<tracking></span></span>  
<span data-ttu-id="782d8-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="782d8-108">\<trackingProfile></span></span>  
<span data-ttu-id="782d8-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="782d8-109">\<workflow></span></span>  
<span data-ttu-id="782d8-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="782d8-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="782d8-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="782d8-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="782d8-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="782d8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="782d8-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="782d8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="782d8-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="782d8-114">Attributes</span></span>  
 <span data-ttu-id="782d8-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="782d8-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="782d8-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="782d8-116">Child Elements</span></span>  
  
|<span data-ttu-id="782d8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="782d8-117">Element</span></span>|<span data-ttu-id="782d8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="782d8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="782d8-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="782d8-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="782d8-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="782d8-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="782d8-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="782d8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="782d8-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="782d8-122">Element</span></span>|<span data-ttu-id="782d8-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="782d8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="782d8-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="782d8-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="782d8-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="782d8-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="782d8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="782d8-126">See Also</span></span>  
 <span data-ttu-id="782d8-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="782d8-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="782d8-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="782d8-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="782d8-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="782d8-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="782d8-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="782d8-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
