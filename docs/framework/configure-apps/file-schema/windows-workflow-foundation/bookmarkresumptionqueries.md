---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398867"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="d9a75-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="d9a75-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="d9a75-102">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9a75-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d9a75-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="d9a75-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="d9a75-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="d9a75-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d9a75-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d9a75-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d9a75-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d9a75-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="d9a75-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="d9a75-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="d9a75-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="d9a75-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="d9a75-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d9a75-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="d9a75-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQueries**</span><span class="sxs-lookup"><span data-stu-id="d9a75-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="d9a75-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9a75-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9a75-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9a75-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d9a75-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9a75-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9a75-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9a75-114">Attributes</span></span>  
 <span data-ttu-id="d9a75-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9a75-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9a75-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9a75-116">Child Elements</span></span>  
  
|<span data-ttu-id="d9a75-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9a75-117">Element</span></span>|<span data-ttu-id="d9a75-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d9a75-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9a75-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="d9a75-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="d9a75-120">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9a75-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="d9a75-121">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="d9a75-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9a75-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9a75-122">Parent Elements</span></span>  
  
|<span data-ttu-id="d9a75-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9a75-123">Element</span></span>|<span data-ttu-id="d9a75-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d9a75-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9a75-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d9a75-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="d9a75-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="d9a75-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9a75-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9a75-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d9a75-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d9a75-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d9a75-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d9a75-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
