---
title: '&lt;cancelRequestedQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 40fbcafd641e93be6ba21635f4f6e6428be62c12
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373327"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="06890-102">&lt;cancelRequestedQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="06890-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="06890-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="06890-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="06890-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="06890-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="06890-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="06890-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="06890-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="06890-106">\<system.serviceModel></span></span>  
<span data-ttu-id="06890-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="06890-107">\<tracking></span></span>  
<span data-ttu-id="06890-108">\<perfiles > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="06890-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="06890-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="06890-109">\<workflow></span></span>  
<span data-ttu-id="06890-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="06890-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06890-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06890-111">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="06890-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06890-112">Attributes and elements</span></span>  

<span data-ttu-id="06890-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06890-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06890-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="06890-114">Attributes</span></span>

<span data-ttu-id="06890-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06890-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="06890-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06890-116">Child elements</span></span>
  
|<span data-ttu-id="06890-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="06890-117">Element</span></span>|<span data-ttu-id="06890-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="06890-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06890-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="06890-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="06890-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="06890-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06890-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06890-121">Parent elements</span></span>  
  
|<span data-ttu-id="06890-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="06890-122">Element</span></span>|<span data-ttu-id="06890-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="06890-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="06890-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="06890-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="06890-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="06890-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06890-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="06890-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="06890-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="06890-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06890-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="06890-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
