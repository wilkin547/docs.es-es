---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bf209525bcc9748e9a5f5b71a0407a4eca1a897
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="dc1c5-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="dc1c5-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="dc1c5-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dc1c5-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="dc1c5-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dc1c5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dc1c5-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dc1c5-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-107">\<tracking></span></span>  
<span data-ttu-id="dc1c5-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-108">\<trackingProfile></span></span>  
<span data-ttu-id="dc1c5-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-109">\<workflow></span></span>  
<span data-ttu-id="dc1c5-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="dc1c5-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc1c5-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc1c5-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc1c5-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc1c5-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dc1c5-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc1c5-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc1c5-115">Attributes</span></span>  
 <span data-ttu-id="dc1c5-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc1c5-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc1c5-117">Child Elements</span></span>  
  
|<span data-ttu-id="dc1c5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc1c5-118">Element</span></span>|<span data-ttu-id="dc1c5-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc1c5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc1c5-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="dc1c5-121">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="dc1c5-122">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc1c5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc1c5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dc1c5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc1c5-124">Element</span></span>|<span data-ttu-id="dc1c5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc1c5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc1c5-126">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="dc1c5-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dc1c5-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="dc1c5-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc1c5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc1c5-128">See Also</span></span>  
 <span data-ttu-id="dc1c5-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dc1c5-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dc1c5-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dc1c5-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="dc1c5-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc1c5-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dc1c5-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dc1c5-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
