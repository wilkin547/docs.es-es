---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: ae6a81123379ecd0e7fdc72f4e115a462f81eb90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555042"
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="46de2-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="46de2-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="46de2-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="46de2-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="46de2-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="46de2-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="46de2-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="46de2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="46de2-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="46de2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="46de2-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="46de2-107">\<tracking></span></span>  
<span data-ttu-id="46de2-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="46de2-108">\<trackingProfile></span></span>  
<span data-ttu-id="46de2-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="46de2-109">\<workflow></span></span>  
<span data-ttu-id="46de2-110">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="46de2-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="46de2-111">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="46de2-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46de2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46de2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46de2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46de2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="46de2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46de2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46de2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="46de2-115">Attributes</span></span>  
 <span data-ttu-id="46de2-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46de2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46de2-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="46de2-117">Child Elements</span></span>  
  
|<span data-ttu-id="46de2-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="46de2-118">Element</span></span>|<span data-ttu-id="46de2-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="46de2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46de2-120">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="46de2-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="46de2-121">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="46de2-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="46de2-122">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="46de2-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46de2-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="46de2-123">Parent Elements</span></span>  
  
|<span data-ttu-id="46de2-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="46de2-124">Element</span></span>|<span data-ttu-id="46de2-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="46de2-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46de2-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="46de2-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="46de2-127">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="46de2-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46de2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="46de2-128">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="46de2-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="46de2-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="46de2-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="46de2-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
