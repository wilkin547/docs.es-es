---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163168"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="21c81-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="21c81-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="21c81-102">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="21c81-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="21c81-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="21c81-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="21c81-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="21c81-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="21c81-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="21c81-105">\<system.serviceModel></span></span>  
<span data-ttu-id="21c81-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="21c81-106">\<tracking></span></span>  
<span data-ttu-id="21c81-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="21c81-107">\<trackingProfile></span></span>  
<span data-ttu-id="21c81-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="21c81-108">\<workflow></span></span>  
<span data-ttu-id="21c81-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="21c81-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21c81-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21c81-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21c81-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21c81-111">Attributes and Elements</span></span>  
 <span data-ttu-id="21c81-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21c81-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21c81-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="21c81-113">Attributes</span></span>  
 <span data-ttu-id="21c81-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="21c81-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="21c81-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21c81-115">Child Elements</span></span>  
  
|<span data-ttu-id="21c81-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="21c81-116">Element</span></span>|<span data-ttu-id="21c81-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="21c81-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21c81-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="21c81-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="21c81-119">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="21c81-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="21c81-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21c81-120">Parent Elements</span></span>  
  
|<span data-ttu-id="21c81-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="21c81-121">Element</span></span>|<span data-ttu-id="21c81-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="21c81-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="21c81-123">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="21c81-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="21c81-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="21c81-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="21c81-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="21c81-125">See also</span></span>

- [<span data-ttu-id="21c81-126">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="21c81-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="21c81-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="21c81-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
