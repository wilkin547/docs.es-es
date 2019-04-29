---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790421"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="367ae-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="367ae-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="367ae-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="367ae-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="367ae-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="367ae-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="367ae-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="367ae-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="367ae-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="367ae-105">\<system.serviceModel></span></span>  
<span data-ttu-id="367ae-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="367ae-106">\<tracking></span></span>  
<span data-ttu-id="367ae-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="367ae-107">\<trackingProfile></span></span>  
<span data-ttu-id="367ae-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="367ae-108">\<workflow></span></span>  
<span data-ttu-id="367ae-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="367ae-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="367ae-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="367ae-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="367ae-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="367ae-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="367ae-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="367ae-112">Attributes and Elements</span></span>  
 <span data-ttu-id="367ae-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="367ae-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="367ae-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="367ae-114">Attributes</span></span>  
  
|<span data-ttu-id="367ae-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="367ae-115">Attribute</span></span>|<span data-ttu-id="367ae-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="367ae-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="367ae-117">activityName</span><span class="sxs-lookup"><span data-stu-id="367ae-117">activityName</span></span>|<span data-ttu-id="367ae-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="367ae-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="367ae-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="367ae-119">childActivityName</span></span>|<span data-ttu-id="367ae-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="367ae-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="367ae-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="367ae-121">Child Elements</span></span>  
 <span data-ttu-id="367ae-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="367ae-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="367ae-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="367ae-123">Parent Elements</span></span>  
  
|<span data-ttu-id="367ae-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="367ae-124">Element</span></span>|<span data-ttu-id="367ae-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="367ae-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="367ae-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="367ae-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="367ae-127">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="367ae-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="367ae-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="367ae-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="367ae-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="367ae-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="367ae-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="367ae-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
