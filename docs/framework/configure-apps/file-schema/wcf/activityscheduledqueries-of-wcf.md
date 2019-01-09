---
title: '&lt;activityScheduledQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: d6bc2360ccdeebe291de495e6ee5c7e22f26590a
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145580"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="5c9b8-102">&lt;activityScheduledQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="5c9b8-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="5c9b8-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="5c9b8-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="5c9b8-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5c9b8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5c9b8-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5c9b8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5c9b8-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-107">\<tracking></span></span>  
<span data-ttu-id="5c9b8-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-108">\<profiles></span></span>  
<span data-ttu-id="5c9b8-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-109">\<trackingProfile></span></span>  
<span data-ttu-id="5c9b8-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-110">\<workflow></span></span>  
<span data-ttu-id="5c9b8-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c9b8-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c9b8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c9b8-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c9b8-113">Attributes and elements</span></span>  

<span data-ttu-id="5c9b8-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c9b8-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c9b8-115">Attributes</span></span>  

<span data-ttu-id="5c9b8-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c9b8-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c9b8-117">Child elements</span></span>  
  
|<span data-ttu-id="5c9b8-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c9b8-118">Element</span></span>|<span data-ttu-id="5c9b8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c9b8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c9b8-120">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="5c9b8-121">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c9b8-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c9b8-122">Parent elements</span></span>  
  
|<span data-ttu-id="5c9b8-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c9b8-123">Element</span></span>|<span data-ttu-id="5c9b8-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c9b8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5c9b8-125">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="5c9b8-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5c9b8-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="5c9b8-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5c9b8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c9b8-127">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="5c9b8-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5c9b8-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5c9b8-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5c9b8-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
