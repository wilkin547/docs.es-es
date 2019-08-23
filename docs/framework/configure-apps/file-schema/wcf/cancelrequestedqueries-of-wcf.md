---
title: <cancelRequestedQueries>de WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 0f04fc928358c96ca3112422f1a6ccd039269e47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926244"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="80f68-102">\<cancelRequestedQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="80f68-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="80f68-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80f68-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="80f68-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="80f68-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="80f68-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="80f68-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="80f68-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="80f68-106">\<system.serviceModel></span></span>  
<span data-ttu-id="80f68-107">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="80f68-107">\<tracking></span></span>  
<span data-ttu-id="80f68-108">\<perfiles > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="80f68-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="80f68-109">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="80f68-109">\<workflow></span></span>  
<span data-ttu-id="80f68-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="80f68-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f68-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="80f68-111">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80f68-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="80f68-112">Attributes and elements</span></span>  

<span data-ttu-id="80f68-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="80f68-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80f68-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="80f68-114">Attributes</span></span>

<span data-ttu-id="80f68-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="80f68-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="80f68-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="80f68-116">Child elements</span></span>
  
|<span data-ttu-id="80f68-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="80f68-117">Element</span></span>|<span data-ttu-id="80f68-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="80f68-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80f68-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="80f68-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="80f68-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="80f68-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80f68-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="80f68-121">Parent elements</span></span>  
  
|<span data-ttu-id="80f68-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="80f68-122">Element</span></span>|<span data-ttu-id="80f68-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="80f68-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80f68-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="80f68-124">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="80f68-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="80f68-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80f68-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="80f68-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="80f68-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="80f68-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="80f68-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="80f68-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
