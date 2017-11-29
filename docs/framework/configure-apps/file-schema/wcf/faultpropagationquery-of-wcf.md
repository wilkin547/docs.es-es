---
title: '&lt;faultPropagationQuery&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 650be6a52651f9f55a868d135fd7d0dfa84b967a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="3f3eb-102">&lt;faultPropagationQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="3f3eb-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="3f3eb-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3f3eb-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3f3eb-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3f3eb-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="3f3eb-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3f3eb-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="3f3eb-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3f3eb-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-109">\<tracking></span></span>  
<span data-ttu-id="3f3eb-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-110">\<trackingProfile></span></span>  
<span data-ttu-id="3f3eb-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-111">\<workflow></span></span>  
<span data-ttu-id="3f3eb-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="3f3eb-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f3eb-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3f3eb-114">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f3eb-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3f3eb-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3f3eb-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f3eb-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="3f3eb-117">Attributes</span></span>  
  
|<span data-ttu-id="3f3eb-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="3f3eb-118">Attribute</span></span>|<span data-ttu-id="3f3eb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f3eb-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f3eb-120">activityName</span><span class="sxs-lookup"><span data-stu-id="3f3eb-120">activityName</span></span>|<span data-ttu-id="3f3eb-121">Una cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="3f3eb-122">El valor predeterminado es *, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="3f3eb-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="3f3eb-123">faultHandlerActivityName</span></span>|<span data-ttu-id="3f3eb-124">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f3eb-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3f3eb-125">Child Elements</span></span>  
 <span data-ttu-id="3f3eb-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f3eb-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3f3eb-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3f3eb-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="3f3eb-128">Element</span></span>|<span data-ttu-id="3f3eb-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="3f3eb-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f3eb-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3f3eb-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="3f3eb-131">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3f3eb-132">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="3f3eb-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3f3eb-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f3eb-133">See Also</span></span>  
 <span data-ttu-id="3f3eb-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3f3eb-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3f3eb-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3f3eb-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3f3eb-136">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3f3eb-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3f3eb-137">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3f3eb-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
