---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 047d13bc8477214fa1e3c9ffdbed6785b29da637
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189586"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="6c78d-101">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c78d-101">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="6c78d-102">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="6c78d-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="6c78d-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="6c78d-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="6c78d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c78d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c78d-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6c78d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6c78d-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6c78d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c78d-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6c78d-107">Attributes</span></span>  

 <span data-ttu-id="6c78d-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6c78d-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c78d-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6c78d-109">Child Elements</span></span>  
  
|<span data-ttu-id="6c78d-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c78d-110">Element</span></span>|<span data-ttu-id="6c78d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c78d-111">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="6c78d-112">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6c78d-112">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="6c78d-113">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="6c78d-113">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c78d-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6c78d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="6c78d-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6c78d-115">Element</span></span>|<span data-ttu-id="6c78d-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c78d-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="6c78d-117">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="6c78d-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c78d-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c78d-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c78d-119">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6c78d-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c78d-120">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6c78d-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
