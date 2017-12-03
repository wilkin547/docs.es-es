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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d860474c4a638a347f85c07862c330f58cc30c09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="3ed72-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="3ed72-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="3ed72-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3ed72-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3ed72-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3ed72-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3ed72-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3ed72-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3ed72-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3ed72-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3ed72-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="3ed72-107">\<tracking></span></span>  
<span data-ttu-id="3ed72-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3ed72-108">\<trackingProfile></span></span>  
<span data-ttu-id="3ed72-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3ed72-109">\<workflow></span></span>  
<span data-ttu-id="3ed72-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="3ed72-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed72-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ed72-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ed72-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3ed72-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3ed72-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3ed72-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ed72-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3ed72-114">Attributes</span></span>  
 <span data-ttu-id="3ed72-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3ed72-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3ed72-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3ed72-116">Child Elements</span></span>  
  
|<span data-ttu-id="3ed72-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ed72-117">Element</span></span>|<span data-ttu-id="3ed72-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ed72-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ed72-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="3ed72-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="3ed72-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3ed72-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3ed72-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3ed72-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3ed72-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="3ed72-122">Element</span></span>|<span data-ttu-id="3ed72-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ed72-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ed72-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3ed72-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3ed72-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="3ed72-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ed72-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ed72-126">See Also</span></span>  
 <span data-ttu-id="3ed72-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3ed72-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3ed72-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3ed72-128"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3ed72-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3ed72-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3ed72-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ed72-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
