---
title: <activityScheduledQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850464"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="b007b-102">\<activityScheduledQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="b007b-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="b007b-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b007b-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b007b-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b007b-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b007b-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b007b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b007b-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b007b-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b007b-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="b007b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="b007b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="b007b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="b007b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="b007b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> activityScheduledQueries**](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b007b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="b007b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQuery**</span><span class="sxs-lookup"><span data-stu-id="b007b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b007b-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b007b-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b007b-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b007b-115">Attributes and elements</span></span>  

<span data-ttu-id="b007b-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b007b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b007b-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="b007b-117">Attributes</span></span>  
  
|<span data-ttu-id="b007b-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="b007b-118">Attribute</span></span>|<span data-ttu-id="b007b-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b007b-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b007b-120">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b007b-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b007b-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b007b-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b007b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b007b-122">Child elements</span></span>

<span data-ttu-id="b007b-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b007b-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b007b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b007b-124">Parent elements</span></span>  
  
|<span data-ttu-id="b007b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="b007b-125">Element</span></span>|<span data-ttu-id="b007b-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b007b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b007b-127">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="b007b-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="b007b-128">Colección de consultas que se usan para realizar el seguimiento de una actividad programada para su ejecución mediante una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b007b-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b007b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="b007b-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b007b-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b007b-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b007b-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b007b-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
