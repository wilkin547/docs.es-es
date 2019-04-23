---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143369"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="3641b-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="3641b-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="3641b-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3641b-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3641b-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3641b-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3641b-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3641b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3641b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3641b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3641b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3641b-106">\<tracking></span></span>  
<span data-ttu-id="3641b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3641b-107">\<trackingProfile></span></span>  
<span data-ttu-id="3641b-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3641b-108">\<workflow></span></span>  
<span data-ttu-id="3641b-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="3641b-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="3641b-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="3641b-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3641b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3641b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3641b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3641b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3641b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3641b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3641b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="3641b-114">Attributes</span></span>  
  
|<span data-ttu-id="3641b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="3641b-115">Attribute</span></span>|<span data-ttu-id="3641b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3641b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3641b-117">activityName</span><span class="sxs-lookup"><span data-stu-id="3641b-117">activityName</span></span>|<span data-ttu-id="3641b-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3641b-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3641b-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3641b-119">childActivityName</span></span>|<span data-ttu-id="3641b-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3641b-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3641b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3641b-121">Child Elements</span></span>  
 <span data-ttu-id="3641b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3641b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3641b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3641b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3641b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="3641b-124">Element</span></span>|<span data-ttu-id="3641b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="3641b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3641b-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="3641b-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="3641b-127">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3641b-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3641b-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3641b-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3641b-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3641b-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3641b-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3641b-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
