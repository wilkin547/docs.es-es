---
title: '&lt;activityScheduledQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: fd7830bc178de0693f0632cea3b390d792408ec1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147884"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="b71f6-102">&lt;activityScheduledQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="b71f6-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="b71f6-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b71f6-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b71f6-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b71f6-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b71f6-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b71f6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b71f6-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b71f6-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b71f6-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="b71f6-107">\<tracking></span></span>  
<span data-ttu-id="b71f6-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="b71f6-108">\<profiles></span></span>  
<span data-ttu-id="b71f6-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b71f6-109">\<trackingProfile></span></span>  
<span data-ttu-id="b71f6-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b71f6-110">\<workflow></span></span>  
<span data-ttu-id="b71f6-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="b71f6-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="b71f6-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="b71f6-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b71f6-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b71f6-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b71f6-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b71f6-114">Attributes and elements</span></span>  

<span data-ttu-id="b71f6-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b71f6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b71f6-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="b71f6-116">Attributes</span></span>  
  
|<span data-ttu-id="b71f6-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="b71f6-117">Attribute</span></span>|<span data-ttu-id="b71f6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b71f6-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b71f6-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b71f6-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b71f6-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b71f6-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b71f6-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b71f6-121">Child elements</span></span>

<span data-ttu-id="b71f6-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b71f6-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b71f6-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b71f6-123">Parent elements</span></span>  
  
|<span data-ttu-id="b71f6-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="b71f6-124">Element</span></span>|<span data-ttu-id="b71f6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="b71f6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b71f6-126">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="b71f6-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="b71f6-127">Una colección de consultas que se usan para realizar un seguimiento de una actividad programada para ejecutarse en una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b71f6-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b71f6-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="b71f6-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b71f6-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b71f6-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b71f6-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b71f6-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
