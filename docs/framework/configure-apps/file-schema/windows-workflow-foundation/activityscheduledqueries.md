---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152429"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="a9fa4-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="a9fa4-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="a9fa4-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="a9fa4-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="a9fa4-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a9fa4-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="a9fa4-104">Para obtener más información sobre el seguimiento de consultas de perfiles, consulte Seguimiento de [perfiles](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a9fa4-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a9fa4-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="a9fa4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="a9fa4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="a9fa4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="a9fa4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="a9fa4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span><span class="sxs-lookup"><span data-stu-id="a9fa4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fa4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9fa4-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a9fa4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a9fa4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a9fa4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a9fa4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a9fa4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="a9fa4-114">Attributes</span></span>  
 <span data-ttu-id="a9fa4-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a9fa4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a9fa4-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a9fa4-116">Child Elements</span></span>  
  
|<span data-ttu-id="a9fa4-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9fa4-117">Element</span></span>|<span data-ttu-id="a9fa4-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9fa4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9fa4-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="a9fa4-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="a9fa4-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="a9fa4-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a9fa4-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a9fa4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a9fa4-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="a9fa4-122">Element</span></span>|<span data-ttu-id="a9fa4-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9fa4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a9fa4-124">\<flujo de trabajo></span><span class="sxs-lookup"><span data-stu-id="a9fa4-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="a9fa4-125">Elemento de configuración que contiene todas las consultas de un flujo de trabajo específico identificado por la propiedad **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="a9fa4-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a9fa4-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9fa4-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a9fa4-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a9fa4-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a9fa4-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a9fa4-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
