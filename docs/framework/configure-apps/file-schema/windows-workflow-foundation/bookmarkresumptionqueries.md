---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: b0ce29213f1f281e8581b90dda17aba1bdc29072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="ce15e-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="ce15e-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="ce15e-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce15e-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ce15e-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="ce15e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ce15e-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ce15e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ce15e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce15e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ce15e-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="ce15e-107">\<tracking></span></span>  
<span data-ttu-id="ce15e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ce15e-108">\<trackingProfile></span></span>  
<span data-ttu-id="ce15e-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="ce15e-109">\<workflow></span></span>  
<span data-ttu-id="ce15e-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ce15e-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="ce15e-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ce15e-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce15e-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce15e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce15e-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ce15e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ce15e-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ce15e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce15e-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="ce15e-115">Attributes</span></span>  
 <span data-ttu-id="ce15e-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ce15e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce15e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ce15e-117">Child Elements</span></span>  
  
|<span data-ttu-id="ce15e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce15e-118">Element</span></span>|<span data-ttu-id="ce15e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce15e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce15e-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ce15e-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="ce15e-121">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ce15e-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ce15e-122">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="ce15e-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce15e-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ce15e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ce15e-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ce15e-124">Element</span></span>|<span data-ttu-id="ce15e-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce15e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce15e-126">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="ce15e-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ce15e-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="ce15e-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce15e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce15e-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="ce15e-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ce15e-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ce15e-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ce15e-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
