---
title: <bookmarkResumptionQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: ee8457645a0b54e21ef27c2891ebea97d6cc547b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926355"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="4631c-102">\<bookmarkResumptionQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="4631c-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="4631c-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4631c-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="4631c-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="4631c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="4631c-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4631c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="4631c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4631c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4631c-107">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4631c-107">\<tracking></span></span>  
<span data-ttu-id="4631c-108">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="4631c-108">\<profiles></span></span>  
<span data-ttu-id="4631c-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4631c-109">\<trackingProfile></span></span>  
<span data-ttu-id="4631c-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4631c-110">\<workflow></span></span>  
<span data-ttu-id="4631c-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="4631c-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="4631c-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="4631c-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4631c-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4631c-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4631c-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4631c-114">Attributes and elements</span></span>

<span data-ttu-id="4631c-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4631c-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4631c-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="4631c-116">Attributes</span></span>  
  
|<span data-ttu-id="4631c-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="4631c-117">Attribute</span></span>|<span data-ttu-id="4631c-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4631c-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4631c-119">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="4631c-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4631c-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4631c-120">Child elements</span></span>

<span data-ttu-id="4631c-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4631c-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="4631c-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4631c-122">Parent elements</span></span>  
  
|<span data-ttu-id="4631c-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4631c-123">Element</span></span>|<span data-ttu-id="4631c-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4631c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4631c-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="4631c-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="4631c-126">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4631c-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4631c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4631c-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4631c-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="4631c-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4631c-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4631c-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
