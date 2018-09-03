---
title: '&lt;cancelRequestedQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: c9266d9ce1f6a61c4468fd95467e76730b966249
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480631"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="9709b-102">&lt;cancelRequestedQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="9709b-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="9709b-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9709b-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9709b-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="9709b-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="9709b-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9709b-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="9709b-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9709b-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9709b-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="9709b-107">\<tracking></span></span>  
<span data-ttu-id="9709b-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9709b-108">\<trackingProfile></span></span>  
<span data-ttu-id="9709b-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9709b-109">\<workflow></span></span>  
<span data-ttu-id="9709b-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="9709b-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9709b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9709b-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9709b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9709b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9709b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9709b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9709b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9709b-114">Attributes</span></span>  
 <span data-ttu-id="9709b-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9709b-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9709b-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9709b-116">Child Elements</span></span>  
  
|<span data-ttu-id="9709b-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9709b-117">Element</span></span>|<span data-ttu-id="9709b-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9709b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9709b-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="9709b-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="9709b-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9709b-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9709b-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9709b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9709b-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9709b-122">Element</span></span>|<span data-ttu-id="9709b-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9709b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9709b-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9709b-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9709b-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="9709b-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9709b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9709b-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="9709b-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9709b-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9709b-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9709b-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
