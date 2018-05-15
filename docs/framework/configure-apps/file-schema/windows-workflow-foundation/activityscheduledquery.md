---
title: '&lt;activityScheduledQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 0822d0ce7dd82ff396596a0ed2431a5f2084ad8f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="1493a-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="1493a-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="1493a-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="1493a-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1493a-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="1493a-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1493a-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1493a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1493a-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1493a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="1493a-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1493a-107">\<tracking></span></span>  
<span data-ttu-id="1493a-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1493a-108">\<trackingProfile></span></span>  
<span data-ttu-id="1493a-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1493a-109">\<workflow></span></span>  
<span data-ttu-id="1493a-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="1493a-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="1493a-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="1493a-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1493a-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1493a-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1493a-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1493a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1493a-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1493a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1493a-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="1493a-115">Attributes</span></span>  
  
|<span data-ttu-id="1493a-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="1493a-116">Attribute</span></span>|<span data-ttu-id="1493a-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="1493a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1493a-118">activityName</span><span class="sxs-lookup"><span data-stu-id="1493a-118">activityName</span></span>|<span data-ttu-id="1493a-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="1493a-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="1493a-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="1493a-120">childActivityName</span></span>|<span data-ttu-id="1493a-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="1493a-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1493a-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1493a-122">Child Elements</span></span>  
 <span data-ttu-id="1493a-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1493a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1493a-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1493a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1493a-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1493a-125">Element</span></span>|<span data-ttu-id="1493a-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="1493a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1493a-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="1493a-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="1493a-128">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="1493a-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1493a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="1493a-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="1493a-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1493a-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1493a-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1493a-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
