---
title: '&lt;bookmarkResumptionQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: f0721e7e14d543b1ff212fe59ed6a2de0a8a9968
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2018
ms.locfileid: "49308444"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="30ab5-102">&lt;bookmarkResumptionQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="30ab5-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="30ab5-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30ab5-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="30ab5-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="30ab5-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="30ab5-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="30ab5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="30ab5-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="30ab5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="30ab5-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="30ab5-107">\<tracking></span></span>  
<span data-ttu-id="30ab5-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="30ab5-108">\<profiles></span></span>  
<span data-ttu-id="30ab5-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="30ab5-109">\<trackingProfile></span></span>  
<span data-ttu-id="30ab5-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="30ab5-110">\<workflow></span></span>  
<span data-ttu-id="30ab5-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="30ab5-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="30ab5-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="30ab5-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ab5-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30ab5-113">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="30ab5-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="30ab5-114">Attributes and elements</span></span>

<span data-ttu-id="30ab5-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="30ab5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30ab5-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="30ab5-116">Attributes</span></span>  
  
|<span data-ttu-id="30ab5-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="30ab5-117">Attribute</span></span>|<span data-ttu-id="30ab5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="30ab5-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="30ab5-119">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="30ab5-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30ab5-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="30ab5-120">Child elements</span></span>

<span data-ttu-id="30ab5-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="30ab5-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="30ab5-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="30ab5-122">Parent elements</span></span>  
  
|<span data-ttu-id="30ab5-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="30ab5-123">Element</span></span>|<span data-ttu-id="30ab5-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="30ab5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30ab5-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="30ab5-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="30ab5-126">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="30ab5-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30ab5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="30ab5-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="30ab5-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="30ab5-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="30ab5-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="30ab5-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
