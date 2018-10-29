---
title: '&lt;customTrackingQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 060e2b5c8efd51f6245a39bd9562a69f0111fd41
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50202229"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="1ef1f-102">&lt;customTrackingQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="1ef1f-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="1ef1f-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1ef1f-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1ef1f-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1ef1f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="1ef1f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1ef1f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1ef1f-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-107">\<tracking></span></span>  
<span data-ttu-id="1ef1f-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-108">\<profiles></span></span>  
<span data-ttu-id="1ef1f-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-109">\<trackingProfile></span></span>  
<span data-ttu-id="1ef1f-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-110">\<workflow></span></span>  
<span data-ttu-id="1ef1f-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ef1f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ef1f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ef1f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1ef1f-113">Attributes and elements</span></span>

<span data-ttu-id="1ef1f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ef1f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="1ef1f-115">Attributes</span></span>

<span data-ttu-id="1ef1f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="1ef1f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1ef1f-117">Child elements</span></span>
  
|<span data-ttu-id="1ef1f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ef1f-118">Element</span></span>|<span data-ttu-id="1ef1f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ef1f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ef1f-120">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="1ef1f-121">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ef1f-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1ef1f-122">Parent elements</span></span>  
  
|<span data-ttu-id="1ef1f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="1ef1f-123">Element</span></span>|<span data-ttu-id="1ef1f-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ef1f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ef1f-125">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1ef1f-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1ef1f-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="1ef1f-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ef1f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ef1f-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="1ef1f-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1ef1f-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="1ef1f-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1ef1f-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
