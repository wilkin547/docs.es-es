---
title: <activityScheduledQuery> de WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 5087d56092296f8c68b719ec0945993adeb3de0a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272908"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="d97ae-102">\<activityScheduledQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="d97ae-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="d97ae-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d97ae-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="d97ae-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="d97ae-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="d97ae-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d97ae-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d97ae-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d97ae-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d97ae-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d97ae-107">\<tracking></span></span>  
<span data-ttu-id="d97ae-108">\<profiles></span><span class="sxs-lookup"><span data-stu-id="d97ae-108">\<profiles></span></span>  
<span data-ttu-id="d97ae-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d97ae-109">\<trackingProfile></span></span>  
<span data-ttu-id="d97ae-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="d97ae-110">\<workflow></span></span>  
<span data-ttu-id="d97ae-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d97ae-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="d97ae-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="d97ae-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d97ae-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d97ae-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d97ae-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d97ae-114">Attributes and elements</span></span>  

<span data-ttu-id="d97ae-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d97ae-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d97ae-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="d97ae-116">Attributes</span></span>  
  
|<span data-ttu-id="d97ae-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="d97ae-117">Attribute</span></span>|<span data-ttu-id="d97ae-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d97ae-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d97ae-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="d97ae-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="d97ae-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="d97ae-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d97ae-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d97ae-121">Child elements</span></span>

<span data-ttu-id="d97ae-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d97ae-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d97ae-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d97ae-123">Parent elements</span></span>  
  
|<span data-ttu-id="d97ae-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d97ae-124">Element</span></span>|<span data-ttu-id="d97ae-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="d97ae-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d97ae-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="d97ae-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="d97ae-127">Una colección de consultas que se usan para realizar un seguimiento de una actividad programada para ejecutarse en una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d97ae-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d97ae-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d97ae-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="d97ae-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d97ae-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d97ae-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d97ae-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
