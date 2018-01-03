---
title: '&lt;customTrackingQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84c9635b37c592b4d82635deb58880d81d2fb5cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="9a27f-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="9a27f-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="9a27f-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9a27f-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9a27f-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="9a27f-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9a27f-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9a27f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9a27f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="9a27f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9a27f-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="9a27f-107">\<tracking></span></span>  
<span data-ttu-id="9a27f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9a27f-108">\<trackingProfile></span></span>  
<span data-ttu-id="9a27f-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9a27f-109">\<workflow></span></span>  
<span data-ttu-id="9a27f-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="9a27f-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a27f-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a27f-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a27f-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a27f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9a27f-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a27f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a27f-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a27f-114">Attributes</span></span>  
 <span data-ttu-id="9a27f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9a27f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a27f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a27f-116">Child Elements</span></span>  
  
|<span data-ttu-id="9a27f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a27f-117">Element</span></span>|<span data-ttu-id="9a27f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a27f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a27f-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="9a27f-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="9a27f-120">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9a27f-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a27f-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a27f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9a27f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a27f-122">Element</span></span>|<span data-ttu-id="9a27f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a27f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a27f-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9a27f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9a27f-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9a27f-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a27f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a27f-126">See Also</span></span>  
 <span data-ttu-id="9a27f-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9a27f-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="9a27f-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="9a27f-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="9a27f-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9a27f-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9a27f-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9a27f-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
