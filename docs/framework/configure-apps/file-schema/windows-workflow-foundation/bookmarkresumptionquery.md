---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398847"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="6c3f2-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="6c3f2-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="6c3f2-102">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="6c3f2-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="6c3f2-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="6c3f2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6c3f2-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6c3f2-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="6c3f2-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="6c3f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="6c3f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="6c3f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> bookmarkResumptionQueries**](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="6c3f2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="6c3f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQuery**</span><span class="sxs-lookup"><span data-stu-id="6c3f2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3f2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c3f2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c3f2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c3f2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6c3f2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c3f2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c3f2-115">Attributes</span></span>  
  
|<span data-ttu-id="6c3f2-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="6c3f2-116">Attribute</span></span>|<span data-ttu-id="6c3f2-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6c3f2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6c3f2-118">Nombre</span><span class="sxs-lookup"><span data-stu-id="6c3f2-118">name</span></span>|<span data-ttu-id="6c3f2-119">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c3f2-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c3f2-120">Child Elements</span></span>  
 <span data-ttu-id="6c3f2-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c3f2-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c3f2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="6c3f2-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c3f2-123">Element</span></span>|<span data-ttu-id="6c3f2-124">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="6c3f2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c3f2-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="6c3f2-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="6c3f2-126">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c3f2-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c3f2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c3f2-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c3f2-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c3f2-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c3f2-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6c3f2-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
