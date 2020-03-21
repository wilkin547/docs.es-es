---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152416"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="cce72-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="cce72-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="cce72-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cce72-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="cce72-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="cce72-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="cce72-104">Para obtener más información sobre el seguimiento de consultas de perfiles, consulte Seguimiento de [perfiles](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cce72-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cce72-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="cce72-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="cce72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="cce72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="cce72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="cce72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="cce72-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span><span class="sxs-lookup"><span data-stu-id="cce72-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cce72-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cce72-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cce72-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cce72-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cce72-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cce72-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cce72-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="cce72-115">Attributes</span></span>  
  
|<span data-ttu-id="cce72-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="cce72-116">Attribute</span></span>|<span data-ttu-id="cce72-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce72-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cce72-118">activityName</span><span class="sxs-lookup"><span data-stu-id="cce72-118">activityName</span></span>|<span data-ttu-id="cce72-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cce72-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="cce72-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="cce72-120">childActivityName</span></span>|<span data-ttu-id="cce72-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cce72-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cce72-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cce72-122">Child Elements</span></span>  
 <span data-ttu-id="cce72-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cce72-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cce72-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cce72-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cce72-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cce72-125">Element</span></span>|<span data-ttu-id="cce72-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cce72-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cce72-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="cce72-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="cce72-128">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cce72-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cce72-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cce72-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="cce72-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cce72-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cce72-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cce72-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
