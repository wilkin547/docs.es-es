---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 2abb2dc05bfec4419ca49d1517084ebc208e81e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="9f75a-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="9f75a-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="9f75a-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9f75a-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9f75a-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="9f75a-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="9f75a-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9f75a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9f75a-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9f75a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9f75a-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="9f75a-107">\<tracking></span></span>  
<span data-ttu-id="9f75a-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9f75a-108">\<trackingProfile></span></span>  
<span data-ttu-id="9f75a-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9f75a-109">\<workflow></span></span>  
<span data-ttu-id="9f75a-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="9f75a-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f75a-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f75a-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f75a-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9f75a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9f75a-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9f75a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f75a-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="9f75a-114">Attributes</span></span>  
 <span data-ttu-id="9f75a-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9f75a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9f75a-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9f75a-116">Child Elements</span></span>  
  
|<span data-ttu-id="9f75a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f75a-117">Element</span></span>|<span data-ttu-id="9f75a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f75a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f75a-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="9f75a-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="9f75a-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9f75a-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f75a-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9f75a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9f75a-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="9f75a-122">Element</span></span>|<span data-ttu-id="9f75a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f75a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f75a-124">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9f75a-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="9f75a-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f75a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f75a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f75a-126">See Also</span></span>  
 [<span data-ttu-id="9f75a-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9f75a-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="9f75a-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9f75a-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
