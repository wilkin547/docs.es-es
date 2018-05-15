---
title: '&lt;activityScheduledQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 4efd6ba13e8a54d3338c25b077477d4abdbe9ab5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="410a4-102">&lt;activityScheduledQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="410a4-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="410a4-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="410a4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="410a4-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="410a4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="410a4-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="410a4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="410a4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="410a4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="410a4-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="410a4-107">\<tracking></span></span>  
<span data-ttu-id="410a4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="410a4-108">\<trackingProfile></span></span>  
<span data-ttu-id="410a4-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="410a4-109">\<workflow></span></span>  
<span data-ttu-id="410a4-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="410a4-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="410a4-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="410a4-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410a4-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="410a4-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="410a4-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="410a4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="410a4-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="410a4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="410a4-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="410a4-115">Attributes</span></span>  
  
|<span data-ttu-id="410a4-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="410a4-116">Attribute</span></span>|<span data-ttu-id="410a4-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="410a4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="410a4-118">activityName</span><span class="sxs-lookup"><span data-stu-id="410a4-118">activityName</span></span>|<span data-ttu-id="410a4-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="410a4-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="410a4-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="410a4-120">childActivityName</span></span>|<span data-ttu-id="410a4-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="410a4-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="410a4-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="410a4-122">Child Elements</span></span>  
 <span data-ttu-id="410a4-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="410a4-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="410a4-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="410a4-124">Parent Elements</span></span>  
  
|<span data-ttu-id="410a4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="410a4-125">Element</span></span>|<span data-ttu-id="410a4-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="410a4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a4-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="410a4-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="410a4-128">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="410a4-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="410a4-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="410a4-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="410a4-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="410a4-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="410a4-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="410a4-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
