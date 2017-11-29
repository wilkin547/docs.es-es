---
title: '&lt;faultPropagationQueries&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e122e8c6194545a02f6db429d550eabed5d49b27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="938ea-102">&lt;faultPropagationQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="938ea-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="938ea-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="938ea-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="938ea-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="938ea-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="938ea-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="938ea-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="938ea-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="938ea-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="938ea-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="938ea-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="938ea-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="938ea-108">\<system.serviceModel></span></span>  
<span data-ttu-id="938ea-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="938ea-109">\<tracking></span></span>  
<span data-ttu-id="938ea-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="938ea-110">\<trackingProfile></span></span>  
<span data-ttu-id="938ea-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="938ea-111">\<workflow></span></span>  
<span data-ttu-id="938ea-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="938ea-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938ea-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="938ea-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="938ea-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="938ea-114">Attributes and Elements</span></span>  
 <span data-ttu-id="938ea-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="938ea-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="938ea-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="938ea-116">Attributes</span></span>  
 <span data-ttu-id="938ea-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="938ea-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="938ea-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="938ea-118">Child Elements</span></span>  
  
|<span data-ttu-id="938ea-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="938ea-119">Element</span></span>|<span data-ttu-id="938ea-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="938ea-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="938ea-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="938ea-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="938ea-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="938ea-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="938ea-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="938ea-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="938ea-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="938ea-124">Parent Elements</span></span>  
  
|<span data-ttu-id="938ea-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="938ea-125">Element</span></span>|<span data-ttu-id="938ea-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="938ea-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="938ea-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="938ea-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="938ea-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="938ea-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="938ea-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="938ea-129">See Also</span></span>  
 <span data-ttu-id="938ea-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="938ea-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="938ea-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="938ea-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="938ea-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="938ea-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="938ea-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="938ea-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
