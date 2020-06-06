---
title: <bookmarkResumptionQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 8cb254599a9742305ec958fd77174f4c4b8a57c2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "71834005"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="9f92f-102">\<bookmarkResumptionQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="9f92f-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="9f92f-103">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9f92f-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="9f92f-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="9f92f-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="9f92f-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9f92f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="9f92f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f92f-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f92f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9f92f-107">Attributes and elements</span></span>

<span data-ttu-id="9f92f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9f92f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f92f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f92f-109">Attributes</span></span>  
  
|<span data-ttu-id="9f92f-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="9f92f-110">Attribute</span></span>|<span data-ttu-id="9f92f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f92f-111">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9f92f-112">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="9f92f-112">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f92f-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9f92f-113">Child elements</span></span>

<span data-ttu-id="9f92f-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9f92f-114">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9f92f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9f92f-115">Parent elements</span></span>  
  
|<span data-ttu-id="9f92f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f92f-116">Element</span></span>|<span data-ttu-id="9f92f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f92f-117">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="9f92f-118">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="9f92f-118">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f92f-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f92f-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9f92f-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9f92f-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9f92f-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9f92f-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
