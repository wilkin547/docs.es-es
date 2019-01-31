---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 049ca79355f13fd4ffacedbb7501d760361f0a81
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282027"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="af91b-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="af91b-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="af91b-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="af91b-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="af91b-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="af91b-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="af91b-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="af91b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="af91b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="af91b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="af91b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="af91b-106">\<tracking></span></span>  
<span data-ttu-id="af91b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="af91b-107">\<trackingProfile></span></span>  
<span data-ttu-id="af91b-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="af91b-108">\<workflow></span></span>  
<span data-ttu-id="af91b-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="af91b-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="af91b-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="af91b-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af91b-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af91b-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af91b-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af91b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="af91b-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af91b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af91b-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="af91b-114">Attributes</span></span>  
  
|<span data-ttu-id="af91b-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="af91b-115">Attribute</span></span>|<span data-ttu-id="af91b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="af91b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af91b-117">activityName</span><span class="sxs-lookup"><span data-stu-id="af91b-117">activityName</span></span>|<span data-ttu-id="af91b-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="af91b-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="af91b-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="af91b-119">childActivityName</span></span>|<span data-ttu-id="af91b-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="af91b-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af91b-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af91b-121">Child Elements</span></span>  
 <span data-ttu-id="af91b-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af91b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af91b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af91b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="af91b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="af91b-124">Element</span></span>|<span data-ttu-id="af91b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="af91b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af91b-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="af91b-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="af91b-127">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="af91b-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="af91b-128">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="af91b-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="af91b-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="af91b-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="af91b-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="af91b-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="af91b-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="af91b-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
