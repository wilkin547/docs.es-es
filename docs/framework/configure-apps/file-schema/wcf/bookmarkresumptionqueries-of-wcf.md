---
description: 'Más información sobre: <bookmarkResumptionQueries> de WCF'
title: <bookmarkResumptionQueries> de WCF
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: dfe631865549915760255b1df22ee970b806e368
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639372"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="351fd-103">\<bookmarkResumptionQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="351fd-103">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="351fd-104">Representa una colección de consultas que se usan para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="351fd-104">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="351fd-105">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="351fd-105">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="351fd-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="351fd-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**  

## <a name="syntax"></a><span data-ttu-id="351fd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="351fd-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="351fd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="351fd-108">Attributes and elements</span></span>  
  
<span data-ttu-id="351fd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="351fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="351fd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="351fd-110">Attributes</span></span>  
  
<span data-ttu-id="351fd-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="351fd-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="351fd-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="351fd-112">Child elements</span></span>  
  
|<span data-ttu-id="351fd-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="351fd-113">Element</span></span>|<span data-ttu-id="351fd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="351fd-114">Description</span></span>|  
|-------------|-----------------|  
|[\<bookmarkResumptionQuery>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="351fd-115">Una consulta que se usa para realizar el seguimiento de la reanudación de un marcador dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="351fd-115">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="351fd-116">La consulta es necesaria para que un participante del seguimiento se suscriba a los registros de reanudación del marcador.</span><span class="sxs-lookup"><span data-stu-id="351fd-116">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="351fd-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="351fd-117">Parent elements</span></span>  
  
|<span data-ttu-id="351fd-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="351fd-118">Element</span></span>|<span data-ttu-id="351fd-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="351fd-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="351fd-120">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="351fd-120">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="351fd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="351fd-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="351fd-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="351fd-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="351fd-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="351fd-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
