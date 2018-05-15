---
title: '&lt;bookmarkResumptionQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 8a83f521e444838b6495221c00211710dd99ab6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="95f7d-102">&lt;bookmarkResumptionQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="95f7d-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="95f7d-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95f7d-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="95f7d-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="95f7d-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="95f7d-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="95f7d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="95f7d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="95f7d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="95f7d-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="95f7d-107">\<tracking></span></span>  
<span data-ttu-id="95f7d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="95f7d-108">\<trackingProfile></span></span>  
<span data-ttu-id="95f7d-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="95f7d-109">\<workflow></span></span>  
<span data-ttu-id="95f7d-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="95f7d-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="95f7d-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="95f7d-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f7d-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95f7d-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="95f7d-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95f7d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="95f7d-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95f7d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95f7d-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="95f7d-115">Attributes</span></span>  
 <span data-ttu-id="95f7d-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="95f7d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95f7d-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95f7d-117">Child Elements</span></span>  
  
|<span data-ttu-id="95f7d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="95f7d-118">Element</span></span>|<span data-ttu-id="95f7d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f7d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95f7d-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="95f7d-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="95f7d-121">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="95f7d-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="95f7d-122">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="95f7d-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95f7d-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95f7d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="95f7d-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="95f7d-124">Element</span></span>|<span data-ttu-id="95f7d-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="95f7d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95f7d-126">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="95f7d-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="95f7d-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="95f7d-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="95f7d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="95f7d-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="95f7d-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="95f7d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="95f7d-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="95f7d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
