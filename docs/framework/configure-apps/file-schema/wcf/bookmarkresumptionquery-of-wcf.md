---
title: <bookmarkResumptionQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 36d169b78e78692c7b45c75d5d375bddbba1c66f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850105"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="7477b-102">\<bookmarkResumptionQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="7477b-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="7477b-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7477b-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="7477b-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="7477b-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="7477b-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="7477b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="7477b-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7477b-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7477b-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="7477b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="7477b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="7477b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="7477b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="7477b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> bookmarkResumptionQueries**](bookmarkresumptionqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="7477b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)</span></span>\
<span data-ttu-id="7477b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> bookmarkResumptionQuery**</span><span class="sxs-lookup"><span data-stu-id="7477b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7477b-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7477b-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7477b-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7477b-115">Attributes and elements</span></span>

<span data-ttu-id="7477b-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7477b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7477b-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="7477b-117">Attributes</span></span>  
  
|<span data-ttu-id="7477b-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="7477b-118">Attribute</span></span>|<span data-ttu-id="7477b-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7477b-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7477b-120">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="7477b-120">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7477b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7477b-121">Child elements</span></span>

<span data-ttu-id="7477b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="7477b-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="7477b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7477b-123">Parent elements</span></span>  
  
|<span data-ttu-id="7477b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="7477b-124">Element</span></span>|<span data-ttu-id="7477b-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7477b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7477b-126">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="7477b-126">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="7477b-127">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7477b-127">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7477b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7477b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7477b-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="7477b-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7477b-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="7477b-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
