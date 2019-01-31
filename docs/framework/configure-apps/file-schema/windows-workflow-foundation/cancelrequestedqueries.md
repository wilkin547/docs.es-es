---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 989d6e99457108336c38fb1eece4c9ac2444c974
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271504"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="cafca-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="cafca-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="cafca-102">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cafca-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="cafca-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="cafca-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="cafca-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cafca-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cafca-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cafca-105">\<system.serviceModel></span></span>  
<span data-ttu-id="cafca-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="cafca-106">\<tracking></span></span>  
<span data-ttu-id="cafca-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="cafca-107">\<trackingProfile></span></span>  
<span data-ttu-id="cafca-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="cafca-108">\<workflow></span></span>  
<span data-ttu-id="cafca-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="cafca-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cafca-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cafca-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cafca-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cafca-111">Attributes and Elements</span></span>  
 <span data-ttu-id="cafca-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cafca-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cafca-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="cafca-113">Attributes</span></span>  
 <span data-ttu-id="cafca-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cafca-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cafca-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cafca-115">Child Elements</span></span>  
  
|<span data-ttu-id="cafca-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="cafca-116">Element</span></span>|<span data-ttu-id="cafca-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cafca-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cafca-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="cafca-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="cafca-119">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cafca-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cafca-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cafca-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cafca-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="cafca-121">Element</span></span>|<span data-ttu-id="cafca-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="cafca-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cafca-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="cafca-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="cafca-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="cafca-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cafca-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="cafca-125">See also</span></span>
- [<span data-ttu-id="cafca-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cafca-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="cafca-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cafca-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
