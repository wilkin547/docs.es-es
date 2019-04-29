---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790278"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="f354c-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="f354c-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="f354c-102">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f354c-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f354c-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="f354c-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="f354c-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f354c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f354c-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f354c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f354c-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="f354c-106">\<tracking></span></span>  
<span data-ttu-id="f354c-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f354c-107">\<trackingProfile></span></span>  
<span data-ttu-id="f354c-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f354c-108">\<workflow></span></span>  
<span data-ttu-id="f354c-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="f354c-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="f354c-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="f354c-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f354c-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f354c-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f354c-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f354c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f354c-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f354c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f354c-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="f354c-114">Attributes</span></span>  
  
|<span data-ttu-id="f354c-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="f354c-115">Attribute</span></span>|<span data-ttu-id="f354c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f354c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f354c-117">name</span><span class="sxs-lookup"><span data-stu-id="f354c-117">name</span></span>|<span data-ttu-id="f354c-118">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="f354c-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f354c-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f354c-119">Child Elements</span></span>  
 <span data-ttu-id="f354c-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f354c-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f354c-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f354c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f354c-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f354c-122">Element</span></span>|<span data-ttu-id="f354c-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f354c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f354c-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="f354c-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="f354c-125">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f354c-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f354c-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f354c-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f354c-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f354c-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f354c-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f354c-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
