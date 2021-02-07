---
description: 'Más información acerca de: <bookmarkResumptionQueries>'
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: e8ff21e2183fe31411674e9d4de6bf3d99d14836
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698159"
---
# \<bookmarkResumptionQueries>

<span data-ttu-id="ef076-102">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef076-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ef076-103">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="ef076-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ef076-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ef076-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="ef076-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef076-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef076-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef076-106">Attributes and Elements</span></span>  

 <span data-ttu-id="ef076-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef076-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef076-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef076-108">Attributes</span></span>  

 <span data-ttu-id="ef076-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef076-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ef076-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef076-110">Child Elements</span></span>  
  
|<span data-ttu-id="ef076-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef076-111">Element</span></span>|<span data-ttu-id="ef076-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef076-112">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery.md)|<span data-ttu-id="ef076-113">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef076-113">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ef076-114">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="ef076-114">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef076-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef076-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ef076-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef076-116">Element</span></span>|<span data-ttu-id="ef076-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef076-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="ef076-118">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="ef076-118">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef076-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef076-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef076-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef076-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef076-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ef076-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
