---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 92060260075017359d8a5f0500d52e52c2217d3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076658"
---
# <a name="customtrackingquery"></a><span data-ttu-id="9d7d5-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9d7d5-101">\<customTrackingQuery></span></span>
<span data-ttu-id="9d7d5-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9d7d5-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9d7d5-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9d7d5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9d7d5-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9d7d5-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9d7d5-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="9d7d5-106">\<tracking></span></span>  
<span data-ttu-id="9d7d5-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="9d7d5-107">\<trackingProfile></span></span>  
<span data-ttu-id="9d7d5-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9d7d5-108">\<workflow></span></span>  
<span data-ttu-id="9d7d5-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="9d7d5-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="9d7d5-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9d7d5-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d7d5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d7d5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d7d5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9d7d5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9d7d5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d7d5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d7d5-114">Attributes</span></span>  
  
|<span data-ttu-id="9d7d5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="9d7d5-115">Attribute</span></span>|<span data-ttu-id="9d7d5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d7d5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d7d5-117">activityName</span><span class="sxs-lookup"><span data-stu-id="9d7d5-117">activityName</span></span>|<span data-ttu-id="9d7d5-118">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="9d7d5-119">name</span><span class="sxs-lookup"><span data-stu-id="9d7d5-119">name</span></span>|<span data-ttu-id="9d7d5-120">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d7d5-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9d7d5-121">Child Elements</span></span>  
 <span data-ttu-id="9d7d5-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d7d5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9d7d5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9d7d5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d7d5-124">Element</span></span>|<span data-ttu-id="9d7d5-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d7d5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9d7d5-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9d7d5-126">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="9d7d5-127">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9d7d5-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d7d5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d7d5-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9d7d5-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9d7d5-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9d7d5-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9d7d5-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
