---
title: <bookmarkResumptionQueries>de WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850130"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="e8bcf-102">\<bookmarkResumptionQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="e8bcf-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="e8bcf-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e8bcf-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="e8bcf-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="e8bcf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="e8bcf-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e8bcf-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e8bcf-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e8bcf-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e8bcf-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8bcf-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="e8bcf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="e8bcf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="e8bcf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8bcf-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="e8bcf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="e8bcf-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="e8bcf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQueries**</span><span class="sxs-lookup"><span data-stu-id="e8bcf-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="e8bcf-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8bcf-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8bcf-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e8bcf-114">Attributes and elements</span></span>  
  
<span data-ttu-id="e8bcf-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8bcf-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="e8bcf-116">Attributes</span></span>  
  
<span data-ttu-id="e8bcf-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8bcf-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e8bcf-118">Child elements</span></span>  
  
|<span data-ttu-id="e8bcf-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8bcf-119">Element</span></span>|<span data-ttu-id="e8bcf-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e8bcf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8bcf-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="e8bcf-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="e8bcf-122">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e8bcf-123">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8bcf-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e8bcf-124">Parent elements</span></span>  
  
|<span data-ttu-id="e8bcf-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="e8bcf-125">Element</span></span>|<span data-ttu-id="e8bcf-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e8bcf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8bcf-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="e8bcf-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="e8bcf-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="e8bcf-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8bcf-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8bcf-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e8bcf-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="e8bcf-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e8bcf-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e8bcf-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
