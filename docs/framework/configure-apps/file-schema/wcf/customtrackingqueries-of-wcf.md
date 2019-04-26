---
title: <customTrackingQueries> de WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704173"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="08f40-102">\<customTrackingQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="08f40-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="08f40-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="08f40-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="08f40-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="08f40-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="08f40-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="08f40-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="08f40-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="08f40-106">\<system.serviceModel></span></span>  
<span data-ttu-id="08f40-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="08f40-107">\<tracking></span></span>  
<span data-ttu-id="08f40-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="08f40-108">\<profiles></span></span>  
<span data-ttu-id="08f40-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="08f40-109">\<trackingProfile></span></span>  
<span data-ttu-id="08f40-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="08f40-110">\<workflow></span></span>  
<span data-ttu-id="08f40-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="08f40-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08f40-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08f40-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08f40-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="08f40-113">Attributes and elements</span></span>

<span data-ttu-id="08f40-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="08f40-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08f40-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="08f40-115">Attributes</span></span>

<span data-ttu-id="08f40-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08f40-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="08f40-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="08f40-117">Child elements</span></span>
  
|<span data-ttu-id="08f40-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="08f40-118">Element</span></span>|<span data-ttu-id="08f40-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="08f40-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08f40-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="08f40-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="08f40-121">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="08f40-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08f40-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="08f40-122">Parent elements</span></span>  
  
|<span data-ttu-id="08f40-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="08f40-123">Element</span></span>|<span data-ttu-id="08f40-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="08f40-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08f40-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="08f40-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="08f40-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="08f40-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08f40-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="08f40-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="08f40-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="08f40-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="08f40-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="08f40-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
