---
title: '&lt;customTrackingQuery&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c88a5d0e15acf67061976826a65faf5bfacb8384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="2dadb-102">&lt;customTrackingQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="2dadb-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="2dadb-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="2dadb-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="2dadb-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="2dadb-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="2dadb-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2dadb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="2dadb-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="2dadb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2dadb-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="2dadb-107">\<tracking></span></span>  
<span data-ttu-id="2dadb-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2dadb-108">\<trackingProfile></span></span>  
<span data-ttu-id="2dadb-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="2dadb-109">\<workflow></span></span>  
<span data-ttu-id="2dadb-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="2dadb-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="2dadb-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="2dadb-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dadb-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2dadb-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="2dadb-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2dadb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2dadb-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2dadb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2dadb-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="2dadb-115">Attributes</span></span>  
  
|<span data-ttu-id="2dadb-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="2dadb-116">Attribute</span></span>|<span data-ttu-id="2dadb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2dadb-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2dadb-118">activityName</span><span class="sxs-lookup"><span data-stu-id="2dadb-118">activityName</span></span>|<span data-ttu-id="2dadb-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2dadb-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="2dadb-120">name</span><span class="sxs-lookup"><span data-stu-id="2dadb-120">name</span></span>|<span data-ttu-id="2dadb-121">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="2dadb-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2dadb-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2dadb-122">Child Elements</span></span>  
 <span data-ttu-id="2dadb-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2dadb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2dadb-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2dadb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2dadb-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2dadb-125">Element</span></span>|<span data-ttu-id="2dadb-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2dadb-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2dadb-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="2dadb-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="2dadb-128">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="2dadb-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2dadb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="2dadb-129">See Also</span></span>  
 <span data-ttu-id="2dadb-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2dadb-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="2dadb-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="2dadb-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="2dadb-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2dadb-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2dadb-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2dadb-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
