---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 88f9639e4ecc3105a0e58d92e443d9582f261970
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756191"
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="b0a3d-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="b0a3d-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="b0a3d-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="b0a3d-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="b0a3d-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b0a3d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b0a3d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b0a3d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b0a3d-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-107">\<tracking></span></span>  
<span data-ttu-id="b0a3d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-108">\<trackingProfile></span></span>  
<span data-ttu-id="b0a3d-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-109">\<workflow></span></span>  
<span data-ttu-id="b0a3d-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="b0a3d-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0a3d-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0a3d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0a3d-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0a3d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b0a3d-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0a3d-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0a3d-115">Attributes</span></span>  
  
|<span data-ttu-id="b0a3d-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0a3d-116">Attribute</span></span>|<span data-ttu-id="b0a3d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0a3d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0a3d-118">name</span><span class="sxs-lookup"><span data-stu-id="b0a3d-118">name</span></span>|<span data-ttu-id="b0a3d-119">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0a3d-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0a3d-120">Child Elements</span></span>  
 <span data-ttu-id="b0a3d-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0a3d-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0a3d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b0a3d-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0a3d-123">Element</span></span>|<span data-ttu-id="b0a3d-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0a3d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0a3d-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="b0a3d-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="b0a3d-126">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0a3d-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0a3d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0a3d-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="b0a3d-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b0a3d-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b0a3d-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b0a3d-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
