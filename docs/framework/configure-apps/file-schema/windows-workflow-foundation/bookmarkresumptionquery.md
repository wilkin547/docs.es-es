---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945961"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="446ef-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="446ef-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="446ef-102">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="446ef-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="446ef-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="446ef-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="446ef-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="446ef-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="446ef-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="446ef-105">\<system.serviceModel></span></span>  
<span data-ttu-id="446ef-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="446ef-106">\<tracking></span></span>  
<span data-ttu-id="446ef-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="446ef-107">\<trackingProfile></span></span>  
<span data-ttu-id="446ef-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="446ef-108">\<workflow></span></span>  
<span data-ttu-id="446ef-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="446ef-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="446ef-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="446ef-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446ef-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="446ef-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="446ef-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="446ef-112">Attributes and Elements</span></span>  
 <span data-ttu-id="446ef-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="446ef-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="446ef-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="446ef-114">Attributes</span></span>  
  
|<span data-ttu-id="446ef-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="446ef-115">Attribute</span></span>|<span data-ttu-id="446ef-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="446ef-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="446ef-117">Nombre</span><span class="sxs-lookup"><span data-stu-id="446ef-117">name</span></span>|<span data-ttu-id="446ef-118">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="446ef-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="446ef-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="446ef-119">Child Elements</span></span>  
 <span data-ttu-id="446ef-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="446ef-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="446ef-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="446ef-121">Parent Elements</span></span>  
  
|<span data-ttu-id="446ef-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="446ef-122">Element</span></span>|<span data-ttu-id="446ef-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="446ef-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="446ef-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="446ef-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="446ef-125">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="446ef-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="446ef-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="446ef-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="446ef-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="446ef-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="446ef-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="446ef-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
