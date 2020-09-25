---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: efd1e4e54223ff9f5d60b4087fbe5b6bebf1af2f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189595"
---
# \<bookmarkResumptionQuery>

<span data-ttu-id="759f5-101">Representa una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="759f5-101">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="759f5-102">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="759f5-102">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="759f5-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="759f5-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="759f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="759f5-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="759f5-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="759f5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="759f5-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="759f5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="759f5-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="759f5-107">Attributes</span></span>  
  
|<span data-ttu-id="759f5-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="759f5-108">Attribute</span></span>|<span data-ttu-id="759f5-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="759f5-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="759f5-110">name</span><span class="sxs-lookup"><span data-stu-id="759f5-110">name</span></span>|<span data-ttu-id="759f5-111">Una cadena que especifica el nombre del registro del marcador al que va a suscribirse.</span><span class="sxs-lookup"><span data-stu-id="759f5-111">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="759f5-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="759f5-112">Child Elements</span></span>  

 <span data-ttu-id="759f5-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="759f5-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="759f5-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="759f5-114">Parent Elements</span></span>  
  
|<span data-ttu-id="759f5-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="759f5-115">Element</span></span>|<span data-ttu-id="759f5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="759f5-116">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQueries>](bookmarkresumptionqueries.md)|<span data-ttu-id="759f5-117">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="759f5-117">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="759f5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="759f5-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="759f5-119">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="759f5-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="759f5-120">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="759f5-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
