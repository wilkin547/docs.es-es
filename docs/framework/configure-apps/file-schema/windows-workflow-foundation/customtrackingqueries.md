---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120086"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="fa07e-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="fa07e-101">\<customTrackingQueries></span></span>
<span data-ttu-id="fa07e-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="fa07e-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="fa07e-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="fa07e-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="fa07e-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fa07e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fa07e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fa07e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="fa07e-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="fa07e-106">\<tracking></span></span>  
<span data-ttu-id="fa07e-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="fa07e-107">\<trackingProfile></span></span>  
<span data-ttu-id="fa07e-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="fa07e-108">\<workflow></span></span>  
<span data-ttu-id="fa07e-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="fa07e-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa07e-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa07e-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa07e-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa07e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa07e-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa07e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa07e-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa07e-113">Attributes</span></span>  
 <span data-ttu-id="fa07e-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa07e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fa07e-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa07e-115">Child Elements</span></span>  
  
|<span data-ttu-id="fa07e-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa07e-116">Element</span></span>|<span data-ttu-id="fa07e-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa07e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa07e-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="fa07e-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="fa07e-119">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="fa07e-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa07e-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa07e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="fa07e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa07e-121">Element</span></span>|<span data-ttu-id="fa07e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa07e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa07e-123">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="fa07e-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="fa07e-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa07e-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fa07e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa07e-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fa07e-126">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fa07e-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fa07e-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fa07e-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
