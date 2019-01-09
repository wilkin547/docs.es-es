---
title: '&lt;bookmarkResumptionQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: ba8c98557a859f4bd37b9aaca80a44c393429da4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146087"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="b544b-102">&lt;bookmarkResumptionQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="b544b-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="b544b-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b544b-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b544b-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="b544b-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="b544b-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b544b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="b544b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b544b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b544b-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="b544b-107">\<tracking></span></span>  
<span data-ttu-id="b544b-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="b544b-108">\<profiles></span></span>  
<span data-ttu-id="b544b-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b544b-109">\<trackingProfile></span></span>  
<span data-ttu-id="b544b-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b544b-110">\<workflow></span></span>  
<span data-ttu-id="b544b-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="b544b-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="b544b-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b544b-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b544b-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b544b-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b544b-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b544b-114">Attributes and elements</span></span>  
  
<span data-ttu-id="b544b-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b544b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b544b-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="b544b-116">Attributes</span></span>  
  
<span data-ttu-id="b544b-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b544b-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b544b-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b544b-118">Child elements</span></span>  
  
|<span data-ttu-id="b544b-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="b544b-119">Element</span></span>|<span data-ttu-id="b544b-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="b544b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b544b-121">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b544b-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="b544b-122">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b544b-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b544b-123">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="b544b-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b544b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b544b-124">Parent elements</span></span>  
  
|<span data-ttu-id="b544b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b544b-125">Element</span></span>|<span data-ttu-id="b544b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="b544b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b544b-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b544b-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b544b-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b544b-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b544b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b544b-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType> 
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="b544b-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b544b-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="b544b-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b544b-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
