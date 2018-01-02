---
title: '&lt;faultPropagationQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da7cf3a439e365c3ee087ffa1739c96041777e98
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="bd1f0-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="bd1f0-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="bd1f0-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="bd1f0-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="bd1f0-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="bd1f0-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="bd1f0-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f0-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="bd1f0-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-108">\<system.serviceModel></span></span>  
<span data-ttu-id="bd1f0-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-109">\<tracking></span></span>  
<span data-ttu-id="bd1f0-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-110">\<trackingProfile></span></span>  
<span data-ttu-id="bd1f0-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-111">\<workflow></span></span>  
<span data-ttu-id="bd1f0-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1f0-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd1f0-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd1f0-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bd1f0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="bd1f0-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd1f0-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="bd1f0-116">Attributes</span></span>  
 <span data-ttu-id="bd1f0-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd1f0-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bd1f0-118">Child Elements</span></span>  
  
|<span data-ttu-id="bd1f0-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd1f0-119">Element</span></span>|<span data-ttu-id="bd1f0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd1f0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd1f0-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="bd1f0-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="bd1f0-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd1f0-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bd1f0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bd1f0-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bd1f0-125">Element</span></span>|<span data-ttu-id="bd1f0-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd1f0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd1f0-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="bd1f0-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="bd1f0-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="bd1f0-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd1f0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd1f0-129">See Also</span></span>  
 <span data-ttu-id="bd1f0-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bd1f0-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="bd1f0-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="bd1f0-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="bd1f0-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="bd1f0-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="bd1f0-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bd1f0-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
