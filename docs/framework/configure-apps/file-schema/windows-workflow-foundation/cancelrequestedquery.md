---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790239"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="6f229-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="6f229-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="6f229-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="6f229-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6f229-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="6f229-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="6f229-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6f229-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6f229-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6f229-105">\<system.serviceModel></span></span>  
<span data-ttu-id="6f229-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6f229-106">\<tracking></span></span>  
<span data-ttu-id="6f229-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6f229-107">\<trackingProfile></span></span>  
<span data-ttu-id="6f229-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="6f229-108">\<workflow></span></span>  
<span data-ttu-id="6f229-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="6f229-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="6f229-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="6f229-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f229-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f229-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f229-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6f229-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6f229-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6f229-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f229-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="6f229-114">Attributes</span></span>  
  
|<span data-ttu-id="6f229-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="6f229-115">Attribute</span></span>|<span data-ttu-id="6f229-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f229-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f229-117">activityName</span><span class="sxs-lookup"><span data-stu-id="6f229-117">activityName</span></span>|<span data-ttu-id="6f229-118">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="6f229-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="6f229-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="6f229-119">childActivityName</span></span>|<span data-ttu-id="6f229-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="6f229-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f229-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6f229-121">Child Elements</span></span>  
 <span data-ttu-id="6f229-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6f229-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f229-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6f229-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6f229-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="6f229-124">Element</span></span>|<span data-ttu-id="6f229-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f229-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f229-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="6f229-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="6f229-127">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="6f229-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6f229-128">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="6f229-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f229-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f229-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6f229-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6f229-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6f229-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6f229-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
