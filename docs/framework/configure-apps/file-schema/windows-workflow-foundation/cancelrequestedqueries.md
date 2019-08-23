---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945951"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="b039b-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="b039b-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="b039b-102">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b039b-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b039b-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="b039b-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="b039b-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b039b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b039b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b039b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b039b-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b039b-106">\<tracking></span></span>  
<span data-ttu-id="b039b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b039b-107">\<trackingProfile></span></span>  
<span data-ttu-id="b039b-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b039b-108">\<workflow></span></span>  
<span data-ttu-id="b039b-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="b039b-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b039b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b039b-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b039b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b039b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b039b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b039b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b039b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b039b-113">Attributes</span></span>  
 <span data-ttu-id="b039b-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b039b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b039b-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b039b-115">Child Elements</span></span>  
  
|<span data-ttu-id="b039b-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b039b-116">Element</span></span>|<span data-ttu-id="b039b-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b039b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b039b-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="b039b-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="b039b-119">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b039b-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b039b-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b039b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b039b-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b039b-121">Element</span></span>|<span data-ttu-id="b039b-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b039b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b039b-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b039b-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="b039b-124">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="b039b-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b039b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b039b-125">See also</span></span>

- [<span data-ttu-id="b039b-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b039b-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b039b-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b039b-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
