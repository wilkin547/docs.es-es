---
title: '&lt;activityScheduledQueries&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a857a86d45226e3dd3805a900612f55078c0bf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="82d01-102">&lt;activityScheduledQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="82d01-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="82d01-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="82d01-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="82d01-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="82d01-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="82d01-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="82d01-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="82d01-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="82d01-106">\<system.serviceModel></span></span>  
<span data-ttu-id="82d01-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="82d01-107">\<tracking></span></span>  
<span data-ttu-id="82d01-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="82d01-108">\<trackingProfile></span></span>  
<span data-ttu-id="82d01-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="82d01-109">\<workflow></span></span>  
<span data-ttu-id="82d01-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="82d01-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82d01-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82d01-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="82d01-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82d01-112">Attributes and Elements</span></span>  
 <span data-ttu-id="82d01-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82d01-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="82d01-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="82d01-114">Attributes</span></span>  
 <span data-ttu-id="82d01-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="82d01-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="82d01-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82d01-116">Child Elements</span></span>  
  
|<span data-ttu-id="82d01-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="82d01-117">Element</span></span>|<span data-ttu-id="82d01-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="82d01-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82d01-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="82d01-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="82d01-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="82d01-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="82d01-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82d01-121">Parent Elements</span></span>  
  
|<span data-ttu-id="82d01-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="82d01-122">Element</span></span>|<span data-ttu-id="82d01-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="82d01-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="82d01-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="82d01-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="82d01-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="82d01-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="82d01-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="82d01-126">See Also</span></span>  
 <span data-ttu-id="82d01-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="82d01-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="82d01-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="82d01-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="82d01-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="82d01-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="82d01-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="82d01-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
