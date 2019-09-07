---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: aa6ee435c66303b5089b459ecc4ed3023297636d
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398971"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="43845-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="43845-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="43845-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="43845-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="43845-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="43845-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="43845-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="43845-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="43845-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43845-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43845-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="43845-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="43845-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="43845-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="43845-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="43845-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="43845-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="43845-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="43845-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityScheduledQueries**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="43845-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="43845-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQuery**</span><span class="sxs-lookup"><span data-stu-id="43845-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43845-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43845-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43845-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43845-113">Attributes and Elements</span></span>  
 <span data-ttu-id="43845-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43845-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43845-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="43845-115">Attributes</span></span>  
  
|<span data-ttu-id="43845-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="43845-116">Attribute</span></span>|<span data-ttu-id="43845-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43845-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43845-118">activityName</span><span class="sxs-lookup"><span data-stu-id="43845-118">activityName</span></span>|<span data-ttu-id="43845-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="43845-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="43845-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="43845-120">childActivityName</span></span>|<span data-ttu-id="43845-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="43845-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43845-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43845-122">Child Elements</span></span>  
 <span data-ttu-id="43845-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43845-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43845-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43845-124">Parent Elements</span></span>  
  
|<span data-ttu-id="43845-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="43845-125">Element</span></span>|<span data-ttu-id="43845-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43845-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43845-127">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="43845-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="43845-128">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="43845-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43845-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="43845-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="43845-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="43845-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="43845-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="43845-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
