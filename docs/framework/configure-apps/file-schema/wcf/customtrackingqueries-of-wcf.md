---
title: '&lt;customTrackingQueries&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a64a155f435fb61c19a50f1b047c7dd28b603716
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="d9ef6-102">&lt;customTrackingQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="d9ef6-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="d9ef6-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="d9ef6-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="d9ef6-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d9ef6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="d9ef6-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d9ef6-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-107">\<tracking></span></span>  
<span data-ttu-id="d9ef6-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-108">\<trackingProfile></span></span>  
<span data-ttu-id="d9ef6-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-109">\<workflow></span></span>  
<span data-ttu-id="d9ef6-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ef6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9ef6-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9ef6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d9ef6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d9ef6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9ef6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d9ef6-114">Attributes</span></span>  
 <span data-ttu-id="d9ef6-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9ef6-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d9ef6-116">Child Elements</span></span>  
  
|<span data-ttu-id="d9ef6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9ef6-117">Element</span></span>|<span data-ttu-id="d9ef6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ef6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ef6-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="d9ef6-120">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9ef6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d9ef6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d9ef6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d9ef6-122">Element</span></span>|<span data-ttu-id="d9ef6-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9ef6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9ef6-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="d9ef6-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d9ef6-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="d9ef6-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9ef6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9ef6-126">See Also</span></span>  
 <span data-ttu-id="d9ef6-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d9ef6-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="d9ef6-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d9ef6-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="d9ef6-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d9ef6-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d9ef6-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d9ef6-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
