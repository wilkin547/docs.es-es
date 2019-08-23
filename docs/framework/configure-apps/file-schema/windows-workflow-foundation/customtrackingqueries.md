---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945836"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="96cf3-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="96cf3-101">\<customTrackingQueries></span></span>
<span data-ttu-id="96cf3-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="96cf3-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="96cf3-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="96cf3-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="96cf3-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="96cf3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="96cf3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="96cf3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="96cf3-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="96cf3-106">\<tracking></span></span>  
<span data-ttu-id="96cf3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="96cf3-107">\<trackingProfile></span></span>  
<span data-ttu-id="96cf3-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="96cf3-108">\<workflow></span></span>  
<span data-ttu-id="96cf3-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="96cf3-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96cf3-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="96cf3-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96cf3-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="96cf3-111">Attributes and Elements</span></span>  
 <span data-ttu-id="96cf3-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="96cf3-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96cf3-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="96cf3-113">Attributes</span></span>  
 <span data-ttu-id="96cf3-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="96cf3-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="96cf3-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="96cf3-115">Child Elements</span></span>  
  
|<span data-ttu-id="96cf3-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="96cf3-116">Element</span></span>|<span data-ttu-id="96cf3-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="96cf3-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96cf3-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="96cf3-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="96cf3-119">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="96cf3-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="96cf3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="96cf3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="96cf3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="96cf3-121">Element</span></span>|<span data-ttu-id="96cf3-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="96cf3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="96cf3-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="96cf3-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="96cf3-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="96cf3-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="96cf3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="96cf3-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="96cf3-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="96cf3-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="96cf3-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="96cf3-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
