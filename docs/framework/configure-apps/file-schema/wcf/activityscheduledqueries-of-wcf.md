---
title: <activityScheduledQueries>de WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850497"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="81403-102">\<activityScheduledQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="81403-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="81403-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="81403-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="81403-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="81403-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="81403-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="81403-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="81403-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="81403-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="81403-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="81403-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="81403-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="81403-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="81403-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="81403-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="81403-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="81403-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="81403-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="81403-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="81403-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> activityScheduledQueries**</span><span class="sxs-lookup"><span data-stu-id="81403-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81403-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81403-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81403-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="81403-114">Attributes and elements</span></span>  

<span data-ttu-id="81403-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="81403-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81403-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="81403-116">Attributes</span></span>  

<span data-ttu-id="81403-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="81403-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="81403-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="81403-118">Child elements</span></span>  
  
|<span data-ttu-id="81403-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="81403-119">Element</span></span>|<span data-ttu-id="81403-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="81403-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81403-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="81403-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="81403-122">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="81403-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="81403-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="81403-123">Parent elements</span></span>  
  
|<span data-ttu-id="81403-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="81403-124">Element</span></span>|<span data-ttu-id="81403-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="81403-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81403-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="81403-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="81403-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="81403-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81403-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="81403-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="81403-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="81403-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81403-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="81403-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
