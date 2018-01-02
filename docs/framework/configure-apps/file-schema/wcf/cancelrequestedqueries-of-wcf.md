---
title: '&lt;cancelRequestedQueries&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f31663d44774f84feab76f22f19400a955a3cf8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="f10b0-102">&lt;cancelRequestedQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="f10b0-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="f10b0-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="f10b0-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f10b0-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="f10b0-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="f10b0-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f10b0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="f10b0-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f10b0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f10b0-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="f10b0-107">\<tracking></span></span>  
<span data-ttu-id="f10b0-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="f10b0-108">\<trackingProfile></span></span>  
<span data-ttu-id="f10b0-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f10b0-109">\<workflow></span></span>  
<span data-ttu-id="f10b0-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="f10b0-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10b0-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f10b0-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f10b0-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f10b0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f10b0-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f10b0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f10b0-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="f10b0-114">Attributes</span></span>  
 <span data-ttu-id="f10b0-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f10b0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f10b0-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f10b0-116">Child Elements</span></span>  
  
|<span data-ttu-id="f10b0-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="f10b0-117">Element</span></span>|<span data-ttu-id="f10b0-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f10b0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f10b0-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="f10b0-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="f10b0-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="f10b0-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f10b0-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f10b0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f10b0-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="f10b0-122">Element</span></span>|<span data-ttu-id="f10b0-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f10b0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f10b0-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="f10b0-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f10b0-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="f10b0-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f10b0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f10b0-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="f10b0-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f10b0-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="f10b0-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f10b0-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
