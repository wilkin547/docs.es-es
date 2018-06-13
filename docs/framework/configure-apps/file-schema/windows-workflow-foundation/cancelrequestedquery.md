---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e532ea482108c9a5cabe13a99afddca10f8341d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767042"
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="2af94-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="2af94-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="2af94-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2af94-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2af94-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2af94-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="2af94-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2af94-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2af94-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2af94-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2af94-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="2af94-107">\<tracking></span></span>  
<span data-ttu-id="2af94-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="2af94-108">\<trackingProfile></span></span>  
<span data-ttu-id="2af94-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="2af94-109">\<workflow></span></span>  
<span data-ttu-id="2af94-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="2af94-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="2af94-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="2af94-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af94-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2af94-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2af94-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2af94-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2af94-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2af94-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2af94-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="2af94-115">Attributes</span></span>  
  
|<span data-ttu-id="2af94-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="2af94-116">Attribute</span></span>|<span data-ttu-id="2af94-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af94-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2af94-118">activityName</span><span class="sxs-lookup"><span data-stu-id="2af94-118">activityName</span></span>|<span data-ttu-id="2af94-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="2af94-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="2af94-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="2af94-120">childActivityName</span></span>|<span data-ttu-id="2af94-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="2af94-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2af94-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2af94-122">Child Elements</span></span>  
 <span data-ttu-id="2af94-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2af94-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2af94-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2af94-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2af94-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="2af94-125">Element</span></span>|<span data-ttu-id="2af94-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af94-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2af94-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="2af94-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="2af94-128">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="2af94-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2af94-129">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="2af94-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2af94-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="2af94-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="2af94-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="2af94-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2af94-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2af94-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
