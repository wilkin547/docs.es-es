---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945881"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="79bda-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="79bda-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="79bda-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="79bda-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="79bda-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="79bda-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="79bda-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="79bda-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="79bda-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="79bda-105">\<system.serviceModel></span></span>  
<span data-ttu-id="79bda-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="79bda-106">\<tracking></span></span>  
<span data-ttu-id="79bda-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="79bda-107">\<trackingProfile></span></span>  
<span data-ttu-id="79bda-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="79bda-108">\<workflow></span></span>  
<span data-ttu-id="79bda-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="79bda-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="79bda-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="79bda-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79bda-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79bda-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79bda-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79bda-112">Attributes and Elements</span></span>  
 <span data-ttu-id="79bda-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79bda-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79bda-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="79bda-114">Attributes</span></span>  
  
|<span data-ttu-id="79bda-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="79bda-115">Attribute</span></span>|<span data-ttu-id="79bda-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="79bda-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79bda-117">activityName</span><span class="sxs-lookup"><span data-stu-id="79bda-117">activityName</span></span>|<span data-ttu-id="79bda-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="79bda-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="79bda-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="79bda-119">childActivityName</span></span>|<span data-ttu-id="79bda-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="79bda-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79bda-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79bda-121">Child Elements</span></span>  
 <span data-ttu-id="79bda-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="79bda-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79bda-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79bda-123">Parent Elements</span></span>  
  
|<span data-ttu-id="79bda-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="79bda-124">Element</span></span>|<span data-ttu-id="79bda-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="79bda-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79bda-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="79bda-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="79bda-127">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="79bda-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="79bda-128">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="79bda-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79bda-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="79bda-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="79bda-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="79bda-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="79bda-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="79bda-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
