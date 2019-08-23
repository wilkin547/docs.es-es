---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945986"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="1deb4-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1deb4-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="1deb4-102">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1deb4-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1deb4-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="1deb4-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="1deb4-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1deb4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1deb4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1deb4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1deb4-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1deb4-106">\<tracking></span></span>  
<span data-ttu-id="1deb4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1deb4-107">\<trackingProfile></span></span>  
<span data-ttu-id="1deb4-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1deb4-108">\<workflow></span></span>  
<span data-ttu-id="1deb4-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="1deb4-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="1deb4-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1deb4-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1deb4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1deb4-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1deb4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1deb4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1deb4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1deb4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1deb4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="1deb4-114">Attributes</span></span>  
 <span data-ttu-id="1deb4-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1deb4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1deb4-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1deb4-116">Child Elements</span></span>  
  
|<span data-ttu-id="1deb4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1deb4-117">Element</span></span>|<span data-ttu-id="1deb4-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1deb4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1deb4-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="1deb4-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="1deb4-120">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1deb4-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="1deb4-121">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="1deb4-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1deb4-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1deb4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1deb4-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1deb4-123">Element</span></span>|<span data-ttu-id="1deb4-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1deb4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1deb4-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1deb4-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1deb4-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="1deb4-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1deb4-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1deb4-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1deb4-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1deb4-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1deb4-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1deb4-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
