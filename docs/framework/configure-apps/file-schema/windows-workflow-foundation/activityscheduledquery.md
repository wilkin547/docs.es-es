---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945504"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="58e71-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="58e71-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="58e71-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="58e71-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="58e71-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="58e71-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="58e71-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="58e71-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="58e71-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="58e71-105">\<system.serviceModel></span></span>  
<span data-ttu-id="58e71-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="58e71-106">\<tracking></span></span>  
<span data-ttu-id="58e71-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="58e71-107">\<trackingProfile></span></span>  
<span data-ttu-id="58e71-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="58e71-108">\<workflow></span></span>  
<span data-ttu-id="58e71-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="58e71-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="58e71-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="58e71-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e71-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58e71-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="58e71-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="58e71-112">Attributes and Elements</span></span>  
 <span data-ttu-id="58e71-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="58e71-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="58e71-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="58e71-114">Attributes</span></span>  
  
|<span data-ttu-id="58e71-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="58e71-115">Attribute</span></span>|<span data-ttu-id="58e71-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="58e71-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="58e71-117">activityName</span><span class="sxs-lookup"><span data-stu-id="58e71-117">activityName</span></span>|<span data-ttu-id="58e71-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="58e71-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="58e71-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="58e71-119">childActivityName</span></span>|<span data-ttu-id="58e71-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="58e71-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="58e71-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="58e71-121">Child Elements</span></span>  
 <span data-ttu-id="58e71-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="58e71-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="58e71-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="58e71-123">Parent Elements</span></span>  
  
|<span data-ttu-id="58e71-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="58e71-124">Element</span></span>|<span data-ttu-id="58e71-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="58e71-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="58e71-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="58e71-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="58e71-127">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="58e71-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="58e71-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="58e71-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="58e71-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="58e71-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="58e71-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="58e71-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
