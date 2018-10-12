---
title: '&lt;activityScheduledQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: a3c4c8b338921c9d949edd83deb4d6073eb26b55
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123376"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="80b9f-102">&lt;activityScheduledQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="80b9f-102">&lt;activityScheduledQuery&gt; of WCF</span></span>

<span data-ttu-id="80b9f-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80b9f-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="80b9f-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="80b9f-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="80b9f-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="80b9f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="80b9f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="80b9f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="80b9f-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="80b9f-107">\<tracking></span></span>  
<span data-ttu-id="80b9f-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="80b9f-108">\<profiles></span></span>  
<span data-ttu-id="80b9f-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="80b9f-109">\<trackingProfile></span></span>  
<span data-ttu-id="80b9f-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="80b9f-110">\<workflow></span></span>  
<span data-ttu-id="80b9f-111">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="80b9f-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="80b9f-112">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="80b9f-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b9f-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80b9f-113">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking> 
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80b9f-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80b9f-114">Attributes and elements</span></span>  

<span data-ttu-id="80b9f-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80b9f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80b9f-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="80b9f-116">Attributes</span></span>  
  
|<span data-ttu-id="80b9f-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="80b9f-117">Attribute</span></span>|<span data-ttu-id="80b9f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b9f-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="80b9f-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="80b9f-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="80b9f-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="80b9f-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80b9f-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80b9f-121">Child elements</span></span>

<span data-ttu-id="80b9f-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80b9f-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="80b9f-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80b9f-123">Parent elements</span></span>  
  
|<span data-ttu-id="80b9f-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="80b9f-124">Element</span></span>|<span data-ttu-id="80b9f-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="80b9f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80b9f-126">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="80b9f-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="80b9f-127">Una colección de consultas que se usan para realizar un seguimiento de una actividad programada para ejecutarse en una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80b9f-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80b9f-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="80b9f-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="80b9f-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="80b9f-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80b9f-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="80b9f-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
