---
title: <activityScheduledQueries> de WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 1c9c292080016d7a2d0014ed07be371c0e247621
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701130"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="6bf62-102">\<activityScheduledQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="6bf62-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="6bf62-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="6bf62-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="6bf62-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="6bf62-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="6bf62-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6bf62-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6bf62-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6bf62-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6bf62-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6bf62-107">\<tracking></span></span>  
<span data-ttu-id="6bf62-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="6bf62-108">\<profiles></span></span>  
<span data-ttu-id="6bf62-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6bf62-109">\<trackingProfile></span></span>  
<span data-ttu-id="6bf62-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="6bf62-110">\<workflow></span></span>  
<span data-ttu-id="6bf62-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="6bf62-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf62-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6bf62-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bf62-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6bf62-113">Attributes and elements</span></span>  

<span data-ttu-id="6bf62-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6bf62-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bf62-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="6bf62-115">Attributes</span></span>  

<span data-ttu-id="6bf62-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6bf62-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6bf62-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6bf62-117">Child elements</span></span>  
  
|<span data-ttu-id="6bf62-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bf62-118">Element</span></span>|<span data-ttu-id="6bf62-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="6bf62-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bf62-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6bf62-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="6bf62-121">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="6bf62-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6bf62-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6bf62-122">Parent elements</span></span>  
  
|<span data-ttu-id="6bf62-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="6bf62-123">Element</span></span>|<span data-ttu-id="6bf62-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="6bf62-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bf62-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6bf62-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6bf62-126">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="6bf62-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bf62-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="6bf62-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="6bf62-128">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6bf62-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6bf62-129">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6bf62-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
