---
title: '&lt;cancelRequestedQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 41964561a460babc41de755e213971593047b707
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748523"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="cc9b7-102">&lt;cancelRequestedQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="cc9b7-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="cc9b7-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="cc9b7-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="cc9b7-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="cc9b7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="cc9b7-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cc9b7-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cc9b7-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-107">\<tracking></span></span>  
<span data-ttu-id="cc9b7-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-108">\<trackingProfile></span></span>  
<span data-ttu-id="cc9b7-109">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-109">\<workflow></span></span>  
<span data-ttu-id="cc9b7-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="cc9b7-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9b7-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc9b7-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cc9b7-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cc9b7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cc9b7-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc9b7-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="cc9b7-115">Attributes</span></span>  
  
|<span data-ttu-id="cc9b7-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="cc9b7-116">Attribute</span></span>|<span data-ttu-id="cc9b7-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc9b7-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc9b7-118">activityName</span><span class="sxs-lookup"><span data-stu-id="cc9b7-118">activityName</span></span>|<span data-ttu-id="cc9b7-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="cc9b7-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="cc9b7-120">childActivityName</span></span>|<span data-ttu-id="cc9b7-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc9b7-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cc9b7-122">Child Elements</span></span>  
 <span data-ttu-id="cc9b7-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc9b7-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cc9b7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="cc9b7-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="cc9b7-125">Element</span></span>|<span data-ttu-id="cc9b7-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc9b7-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc9b7-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="cc9b7-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="cc9b7-128">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="cc9b7-129">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="cc9b7-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc9b7-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc9b7-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="cc9b7-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="cc9b7-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cc9b7-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="cc9b7-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
