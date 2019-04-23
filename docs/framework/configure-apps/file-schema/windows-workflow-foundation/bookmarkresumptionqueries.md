---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109414"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="1ece6-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1ece6-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="1ece6-102">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ece6-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1ece6-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="1ece6-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="1ece6-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1ece6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1ece6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1ece6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1ece6-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1ece6-106">\<tracking></span></span>  
<span data-ttu-id="1ece6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1ece6-107">\<trackingProfile></span></span>  
<span data-ttu-id="1ece6-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1ece6-108">\<workflow></span></span>  
<span data-ttu-id="1ece6-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1ece6-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1ece6-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1ece6-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ece6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ece6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ece6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ece6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1ece6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ece6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ece6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ece6-114">Attributes</span></span>  
 <span data-ttu-id="1ece6-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1ece6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1ece6-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ece6-116">Child Elements</span></span>  
  
|<span data-ttu-id="1ece6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ece6-117">Element</span></span>|<span data-ttu-id="1ece6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ece6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ece6-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1ece6-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="1ece6-120">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1ece6-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1ece6-121">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="1ece6-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ece6-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ece6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1ece6-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ece6-123">Element</span></span>|<span data-ttu-id="1ece6-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ece6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ece6-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1ece6-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1ece6-126">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ece6-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ece6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ece6-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1ece6-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1ece6-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1ece6-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1ece6-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
