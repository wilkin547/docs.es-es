---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e1697b245f9ab61cab3e4b26b1756259f0eba9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="0499f-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0499f-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="0499f-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="0499f-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0499f-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="0499f-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0499f-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0499f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0499f-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0499f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0499f-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="0499f-107">\<tracking></span></span>  
<span data-ttu-id="0499f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0499f-108">\<trackingProfile></span></span>  
<span data-ttu-id="0499f-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="0499f-109">\<workflow></span></span>  
<span data-ttu-id="0499f-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="0499f-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="0499f-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0499f-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0499f-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0499f-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0499f-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0499f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0499f-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0499f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0499f-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="0499f-115">Attributes</span></span>  
  
|<span data-ttu-id="0499f-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="0499f-116">Attribute</span></span>|<span data-ttu-id="0499f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="0499f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0499f-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0499f-118">activityName</span></span>|<span data-ttu-id="0499f-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="0499f-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0499f-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0499f-120">childActivityName</span></span>|<span data-ttu-id="0499f-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="0499f-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0499f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0499f-122">Child Elements</span></span>  
 <span data-ttu-id="0499f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0499f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0499f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0499f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0499f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0499f-125">Element</span></span>|<span data-ttu-id="0499f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="0499f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0499f-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0499f-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0499f-128">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="0499f-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0499f-129">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="0499f-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0499f-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="0499f-130">See Also</span></span>  
 <span data-ttu-id="0499f-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0499f-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="0499f-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0499f-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="0499f-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0499f-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0499f-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0499f-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
