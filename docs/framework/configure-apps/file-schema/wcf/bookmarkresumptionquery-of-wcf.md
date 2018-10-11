---
title: '&lt;bookmarkResumptionQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 07215347da19a05d5915296668d990853fdae646
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087796"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="0a450-102">&lt;bookmarkResumptionQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="0a450-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="0a450-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0a450-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="0a450-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="0a450-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="0a450-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0a450-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0a450-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0a450-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0a450-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="0a450-107">\<tracking></span></span>  
<span data-ttu-id="0a450-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0a450-108">\<trackingProfile></span></span>  
<span data-ttu-id="0a450-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="0a450-109">\<workflow></span></span>  
<span data-ttu-id="0a450-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0a450-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="0a450-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="0a450-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a450-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a450-112">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="0a450-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0a450-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0a450-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0a450-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a450-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="0a450-115">Attributes</span></span>  
  
|<span data-ttu-id="0a450-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="0a450-116">Attribute</span></span>|<span data-ttu-id="0a450-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a450-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a450-118">name</span><span class="sxs-lookup"><span data-stu-id="0a450-118">name</span></span>|<span data-ttu-id="0a450-119">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="0a450-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a450-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0a450-120">Child Elements</span></span>  
 <span data-ttu-id="0a450-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0a450-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a450-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0a450-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0a450-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="0a450-123">Element</span></span>|<span data-ttu-id="0a450-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="0a450-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a450-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="0a450-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="0a450-126">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0a450-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a450-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a450-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="0a450-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0a450-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0a450-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0a450-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
