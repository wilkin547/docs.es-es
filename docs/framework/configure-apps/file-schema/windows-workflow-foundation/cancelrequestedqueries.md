---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163168"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="aa732-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="aa732-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="aa732-102">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="aa732-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="aa732-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="aa732-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="aa732-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="aa732-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="aa732-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aa732-105">\<system.serviceModel></span></span>  
<span data-ttu-id="aa732-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="aa732-106">\<tracking></span></span>  
<span data-ttu-id="aa732-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="aa732-107">\<trackingProfile></span></span>  
<span data-ttu-id="aa732-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="aa732-108">\<workflow></span></span>  
<span data-ttu-id="aa732-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="aa732-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa732-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aa732-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa732-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="aa732-111">Attributes and Elements</span></span>  
 <span data-ttu-id="aa732-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="aa732-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa732-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="aa732-113">Attributes</span></span>  
 <span data-ttu-id="aa732-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="aa732-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="aa732-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="aa732-115">Child Elements</span></span>  
  
|<span data-ttu-id="aa732-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa732-116">Element</span></span>|<span data-ttu-id="aa732-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa732-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa732-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="aa732-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="aa732-119">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="aa732-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa732-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="aa732-120">Parent Elements</span></span>  
  
|<span data-ttu-id="aa732-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="aa732-121">Element</span></span>|<span data-ttu-id="aa732-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="aa732-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa732-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="aa732-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="aa732-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="aa732-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aa732-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa732-125">See also</span></span>

- [<span data-ttu-id="aa732-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="aa732-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aa732-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="aa732-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
