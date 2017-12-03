---
title: '&lt;activityScheduledQuery&gt; de WCF'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 260b77789df6a03b640895ed158c94bfd1533f9b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="cb4bd-102">&lt;activityScheduledQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="cb4bd-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="cb4bd-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="cb4bd-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="cb4bd-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cb4bd-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="cb4bd-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cb4bd-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-107">\<tracking></span></span>  
<span data-ttu-id="cb4bd-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-108">\<trackingProfile></span></span>  
<span data-ttu-id="cb4bd-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-109">\<workflow></span></span>  
<span data-ttu-id="cb4bd-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="cb4bd-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4bd-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb4bd-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb4bd-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cb4bd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cb4bd-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb4bd-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb4bd-115">Attributes</span></span>  
  
|<span data-ttu-id="cb4bd-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="cb4bd-116">Attribute</span></span>|<span data-ttu-id="cb4bd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4bd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb4bd-118">activityName</span><span class="sxs-lookup"><span data-stu-id="cb4bd-118">activityName</span></span>|<span data-ttu-id="cb4bd-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="cb4bd-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="cb4bd-120">childActivityName</span></span>|<span data-ttu-id="cb4bd-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb4bd-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cb4bd-122">Child Elements</span></span>  
 <span data-ttu-id="cb4bd-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cb4bd-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cb4bd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cb4bd-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cb4bd-125">Element</span></span>|<span data-ttu-id="cb4bd-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb4bd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb4bd-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="cb4bd-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="cb4bd-128">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cb4bd-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb4bd-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb4bd-129">See Also</span></span>  
 <span data-ttu-id="cb4bd-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="cb4bd-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="cb4bd-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="cb4bd-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="cb4bd-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cb4bd-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cb4bd-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cb4bd-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
