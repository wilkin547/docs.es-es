---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398975"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="dc6a6-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="dc6a6-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="dc6a6-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="dc6a6-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="dc6a6-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="dc6a6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dc6a6-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc6a6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc6a6-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dc6a6-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="dc6a6-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="dc6a6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="dc6a6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="dc6a6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="dc6a6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dc6a6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="dc6a6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQueries**</span><span class="sxs-lookup"><span data-stu-id="dc6a6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6a6-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc6a6-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc6a6-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc6a6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dc6a6-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc6a6-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc6a6-114">Attributes</span></span>  
 <span data-ttu-id="dc6a6-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc6a6-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc6a6-116">Child Elements</span></span>  
  
|<span data-ttu-id="dc6a6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc6a6-117">Element</span></span>|<span data-ttu-id="dc6a6-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc6a6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc6a6-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="dc6a6-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="dc6a6-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="dc6a6-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc6a6-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc6a6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="dc6a6-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc6a6-122">Element</span></span>|<span data-ttu-id="dc6a6-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dc6a6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc6a6-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dc6a6-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="dc6a6-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="dc6a6-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc6a6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc6a6-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dc6a6-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc6a6-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dc6a6-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dc6a6-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
