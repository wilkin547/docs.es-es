---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 7ddf19ed75d50f3cd5f20de8b0e2dfcdd5ea82b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="64399-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="64399-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="64399-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="64399-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="64399-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="64399-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="64399-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="64399-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="64399-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="64399-106">\<system.serviceModel></span></span>  
<span data-ttu-id="64399-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="64399-107">\<tracking></span></span>  
<span data-ttu-id="64399-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="64399-108">\<trackingProfile></span></span>  
<span data-ttu-id="64399-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="64399-109">\<workflow></span></span>  
<span data-ttu-id="64399-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="64399-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="64399-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="64399-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64399-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64399-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64399-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64399-113">Attributes and Elements</span></span>  
 <span data-ttu-id="64399-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64399-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64399-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="64399-115">Attributes</span></span>  
  
|<span data-ttu-id="64399-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="64399-116">Attribute</span></span>|<span data-ttu-id="64399-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="64399-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64399-118">activityName</span><span class="sxs-lookup"><span data-stu-id="64399-118">activityName</span></span>|<span data-ttu-id="64399-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="64399-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="64399-120">name</span><span class="sxs-lookup"><span data-stu-id="64399-120">name</span></span>|<span data-ttu-id="64399-121">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="64399-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64399-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64399-122">Child Elements</span></span>  
 <span data-ttu-id="64399-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="64399-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64399-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64399-124">Parent Elements</span></span>  
  
|<span data-ttu-id="64399-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="64399-125">Element</span></span>|<span data-ttu-id="64399-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="64399-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64399-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="64399-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="64399-128">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="64399-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64399-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="64399-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>         
 [<span data-ttu-id="64399-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="64399-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="64399-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="64399-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
