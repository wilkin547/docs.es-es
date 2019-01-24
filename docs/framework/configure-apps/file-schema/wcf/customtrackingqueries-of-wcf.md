---
title: '&lt;customTrackingQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: f4f6186aa51ef1656f31fb0035f58a07e5c2447b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700798"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="99778-102">&lt;customTrackingQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="99778-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="99778-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="99778-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="99778-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="99778-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="99778-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="99778-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="99778-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99778-106">\<system.serviceModel></span></span>  
<span data-ttu-id="99778-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="99778-107">\<tracking></span></span>  
<span data-ttu-id="99778-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="99778-108">\<profiles></span></span>  
<span data-ttu-id="99778-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="99778-109">\<trackingProfile></span></span>  
<span data-ttu-id="99778-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="99778-110">\<workflow></span></span>  
<span data-ttu-id="99778-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="99778-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99778-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="99778-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99778-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="99778-113">Attributes and elements</span></span>

<span data-ttu-id="99778-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="99778-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99778-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="99778-115">Attributes</span></span>

<span data-ttu-id="99778-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="99778-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="99778-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="99778-117">Child elements</span></span>
  
|<span data-ttu-id="99778-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="99778-118">Element</span></span>|<span data-ttu-id="99778-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="99778-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99778-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="99778-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="99778-121">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="99778-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99778-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="99778-122">Parent elements</span></span>  
  
|<span data-ttu-id="99778-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="99778-123">Element</span></span>|<span data-ttu-id="99778-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="99778-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99778-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="99778-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="99778-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="99778-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99778-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="99778-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="99778-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="99778-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="99778-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="99778-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
