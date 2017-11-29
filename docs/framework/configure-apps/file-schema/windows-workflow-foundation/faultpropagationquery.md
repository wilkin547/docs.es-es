---
title: '&lt;faultPropagationQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3c9dc0e0580c884377e790fa8c1e9a23de9ecd1c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="1569e-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="1569e-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="1569e-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1569e-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1569e-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="1569e-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1569e-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1569e-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1569e-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="1569e-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="1569e-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1569e-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1569e-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="1569e-108">\<system.serviceModel></span></span>  
<span data-ttu-id="1569e-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1569e-109">\<tracking></span></span>  
<span data-ttu-id="1569e-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1569e-110">\<trackingProfile></span></span>  
<span data-ttu-id="1569e-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1569e-111">\<workflow></span></span>  
<span data-ttu-id="1569e-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="1569e-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="1569e-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="1569e-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1569e-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1569e-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1569e-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1569e-115">Attributes and Elements</span></span>  
 <span data-ttu-id="1569e-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1569e-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1569e-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="1569e-117">Attributes</span></span>  
  
|<span data-ttu-id="1569e-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="1569e-118">Attribute</span></span>|<span data-ttu-id="1569e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1569e-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1569e-120">activityName</span><span class="sxs-lookup"><span data-stu-id="1569e-120">activityName</span></span>|<span data-ttu-id="1569e-121">Una cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="1569e-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="1569e-122">El valor predeterminado es *, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="1569e-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="1569e-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="1569e-123">faultHandlerActivityName</span></span>|<span data-ttu-id="1569e-124">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="1569e-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1569e-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1569e-125">Child Elements</span></span>  
 <span data-ttu-id="1569e-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1569e-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1569e-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1569e-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1569e-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1569e-128">Element</span></span>|<span data-ttu-id="1569e-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="1569e-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1569e-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="1569e-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="1569e-131">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1569e-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1569e-132">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="1569e-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1569e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1569e-133">See Also</span></span>  
 <span data-ttu-id="1569e-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1569e-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="1569e-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="1569e-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="1569e-136">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1569e-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1569e-137">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1569e-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
