---
title: <bookmarkResumptionQueries> de WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 4b11543e240b482d52c157083d1184db4f81bb04
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261280"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="9c776-102">\<bookmarkResumptionQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="9c776-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="9c776-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c776-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9c776-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="9c776-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="9c776-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9c776-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9c776-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9c776-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9c776-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9c776-107">\<tracking></span></span>  
<span data-ttu-id="9c776-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="9c776-108">\<profiles></span></span>  
<span data-ttu-id="9c776-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9c776-109">\<trackingProfile></span></span>  
<span data-ttu-id="9c776-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9c776-110">\<workflow></span></span>  
<span data-ttu-id="9c776-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="9c776-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="9c776-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="9c776-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c776-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c776-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c776-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9c776-114">Attributes and elements</span></span>  
  
<span data-ttu-id="9c776-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9c776-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c776-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="9c776-116">Attributes</span></span>  
  
<span data-ttu-id="9c776-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9c776-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c776-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9c776-118">Child elements</span></span>  
  
|<span data-ttu-id="9c776-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c776-119">Element</span></span>|<span data-ttu-id="9c776-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c776-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c776-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="9c776-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="9c776-122">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9c776-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9c776-123">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="9c776-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c776-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9c776-124">Parent elements</span></span>  
  
|<span data-ttu-id="9c776-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="9c776-125">Element</span></span>|<span data-ttu-id="9c776-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c776-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c776-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9c776-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9c776-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="9c776-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c776-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c776-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9c776-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9c776-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c776-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9c776-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
