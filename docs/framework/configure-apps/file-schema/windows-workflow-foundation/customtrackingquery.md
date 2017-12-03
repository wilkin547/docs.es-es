---
title: '&lt;customTrackingQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 908c340167d50d4d16e0eeff7cc2e01290b55e7a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="5b956-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="5b956-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="5b956-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="5b956-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5b956-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="5b956-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5b956-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5b956-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5b956-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5b956-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5b956-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="5b956-107">\<tracking></span></span>  
<span data-ttu-id="5b956-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5b956-108">\<trackingProfile></span></span>  
<span data-ttu-id="5b956-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="5b956-109">\<workflow></span></span>  
<span data-ttu-id="5b956-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="5b956-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="5b956-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="5b956-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b956-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b956-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b956-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5b956-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5b956-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5b956-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b956-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5b956-115">Attributes</span></span>  
  
|<span data-ttu-id="5b956-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5b956-116">Attribute</span></span>|<span data-ttu-id="5b956-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b956-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b956-118">activityName</span><span class="sxs-lookup"><span data-stu-id="5b956-118">activityName</span></span>|<span data-ttu-id="5b956-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5b956-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="5b956-120">name</span><span class="sxs-lookup"><span data-stu-id="5b956-120">name</span></span>|<span data-ttu-id="5b956-121">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="5b956-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b956-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5b956-122">Child Elements</span></span>  
 <span data-ttu-id="5b956-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5b956-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b956-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5b956-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5b956-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5b956-125">Element</span></span>|<span data-ttu-id="5b956-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b956-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b956-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="5b956-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="5b956-128">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="5b956-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b956-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b956-129">See Also</span></span>  
 <span data-ttu-id="5b956-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5b956-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="5b956-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5b956-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="5b956-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5b956-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="5b956-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5b956-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
