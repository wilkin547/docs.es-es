---
title: '&lt;bookmarkResumptionQueries&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c29f4c0cd92b2c4e8263e1893e7deefc2f14624a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="8b219-102">&lt;bookmarkResumptionQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="8b219-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="8b219-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b219-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8b219-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="8b219-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="8b219-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8b219-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="8b219-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8b219-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8b219-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="8b219-107">\<tracking></span></span>  
<span data-ttu-id="8b219-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8b219-108">\<trackingProfile></span></span>  
<span data-ttu-id="8b219-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="8b219-109">\<workflow></span></span>  
<span data-ttu-id="8b219-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="8b219-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="8b219-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8b219-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b219-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b219-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8b219-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="8b219-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8b219-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="8b219-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b219-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="8b219-115">Attributes</span></span>  
 <span data-ttu-id="8b219-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="8b219-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8b219-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="8b219-117">Child Elements</span></span>  
  
|<span data-ttu-id="8b219-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b219-118">Element</span></span>|<span data-ttu-id="8b219-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b219-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b219-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="8b219-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="8b219-121">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b219-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8b219-122">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="8b219-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b219-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="8b219-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8b219-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="8b219-124">Element</span></span>|<span data-ttu-id="8b219-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b219-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b219-126">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="8b219-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8b219-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="8b219-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b219-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b219-128">See Also</span></span>  
 <span data-ttu-id="8b219-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8b219-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="8b219-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8b219-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="8b219-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="8b219-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8b219-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="8b219-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
