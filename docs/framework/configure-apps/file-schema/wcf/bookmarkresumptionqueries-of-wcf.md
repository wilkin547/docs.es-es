---
title: <bookmarkResumptionQueries>de WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850130"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="00b43-102">\<bookmarkResumptionQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="00b43-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="00b43-103">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="00b43-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="00b43-104">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="00b43-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="00b43-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="00b43-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="00b43-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00b43-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00b43-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="00b43-107">Attributes and elements</span></span>  
  
<span data-ttu-id="00b43-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="00b43-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00b43-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="00b43-109">Attributes</span></span>  
  
<span data-ttu-id="00b43-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="00b43-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="00b43-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="00b43-111">Child elements</span></span>  
  
|<span data-ttu-id="00b43-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b43-112">Element</span></span>|<span data-ttu-id="00b43-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="00b43-113">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="00b43-114">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="00b43-114">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="00b43-115">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="00b43-115">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="00b43-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="00b43-116">Parent elements</span></span>  
  
|<span data-ttu-id="00b43-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="00b43-117">Element</span></span>|<span data-ttu-id="00b43-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="00b43-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="00b43-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="00b43-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="00b43-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="00b43-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="00b43-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="00b43-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="00b43-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="00b43-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
