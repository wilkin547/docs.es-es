---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204047"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="c1ecb-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c1ecb-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="c1ecb-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c1ecb-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="c1ecb-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="c1ecb-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="c1ecb-106">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c1ecb-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c1ecb-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1ecb-107">\<system.serviceModel></span></span>  
<span data-ttu-id="c1ecb-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c1ecb-108">\<tracking></span></span>  
<span data-ttu-id="c1ecb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c1ecb-109">\<trackingProfile></span></span>  
<span data-ttu-id="c1ecb-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="c1ecb-110">\<workflow></span></span>  
<span data-ttu-id="c1ecb-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c1ecb-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1ecb-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1ecb-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1ecb-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1ecb-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c1ecb-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1ecb-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1ecb-115">Attributes</span></span>  
 <span data-ttu-id="c1ecb-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1ecb-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1ecb-117">Child Elements</span></span>  
  
|<span data-ttu-id="c1ecb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1ecb-118">Element</span></span>|<span data-ttu-id="c1ecb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1ecb-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ecb-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c1ecb-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="c1ecb-121">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c1ecb-122">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1ecb-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1ecb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c1ecb-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1ecb-124">Element</span></span>|<span data-ttu-id="c1ecb-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1ecb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1ecb-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c1ecb-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="c1ecb-127">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="c1ecb-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1ecb-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1ecb-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c1ecb-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c1ecb-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c1ecb-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c1ecb-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
