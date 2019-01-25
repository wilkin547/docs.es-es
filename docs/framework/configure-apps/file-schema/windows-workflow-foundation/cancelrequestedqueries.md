---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520690"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="d1f9f-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="d1f9f-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="d1f9f-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d1f9f-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d1f9f-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d1f9f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d1f9f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1f9f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d1f9f-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d1f9f-107">\<tracking></span></span>  
<span data-ttu-id="d1f9f-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d1f9f-108">\<trackingProfile></span></span>  
<span data-ttu-id="d1f9f-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="d1f9f-109">\<workflow></span></span>  
<span data-ttu-id="d1f9f-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d1f9f-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1f9f-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d1f9f-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1f9f-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d1f9f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1f9f-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1f9f-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="d1f9f-114">Attributes</span></span>  
 <span data-ttu-id="d1f9f-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d1f9f-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d1f9f-116">Child Elements</span></span>  
  
|<span data-ttu-id="d1f9f-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1f9f-117">Element</span></span>|<span data-ttu-id="d1f9f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1f9f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1f9f-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d1f9f-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="d1f9f-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d1f9f-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d1f9f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d1f9f-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="d1f9f-122">Element</span></span>|<span data-ttu-id="d1f9f-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="d1f9f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1f9f-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d1f9f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d1f9f-125">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d1f9f-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1f9f-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="d1f9f-126">See also</span></span>
- [<span data-ttu-id="d1f9f-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d1f9f-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d1f9f-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d1f9f-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
