---
description: 'Más información sobre: <bookmarkResumptionQuery> de WCF'
title: <bookmarkResumptionQuery> de WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 9dadab3e304a2507a404bf43c377df46d5b33dda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639333"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="99fff-103">\<bookmarkResumptionQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="99fff-103">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="99fff-104">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="99fff-104">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="99fff-105">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="99fff-105">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="99fff-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="99fff-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="99fff-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99fff-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99fff-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99fff-108">Attributes and elements</span></span>

<span data-ttu-id="99fff-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99fff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99fff-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="99fff-110">Attributes</span></span>  
  
|<span data-ttu-id="99fff-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="99fff-111">Attribute</span></span>|<span data-ttu-id="99fff-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="99fff-112">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="99fff-113">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="99fff-113">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99fff-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99fff-114">Child elements</span></span>

<span data-ttu-id="99fff-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99fff-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="99fff-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99fff-116">Parent elements</span></span>  
  
|<span data-ttu-id="99fff-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="99fff-117">Element</span></span>|<span data-ttu-id="99fff-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="99fff-118">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="99fff-119">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="99fff-119">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99fff-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="99fff-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="99fff-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="99fff-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="99fff-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="99fff-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
