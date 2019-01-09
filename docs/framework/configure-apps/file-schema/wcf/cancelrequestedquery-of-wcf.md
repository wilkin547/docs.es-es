---
title: '&lt;cancelRequestedQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 6b41721dcc0c489377c59bfccdd0b1a617f551b0
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149077"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="9be60-102">&lt;cancelRequestedQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="9be60-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>

<span data-ttu-id="9be60-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9be60-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="9be60-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="9be60-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="9be60-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9be60-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9be60-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9be60-106">\<system.serviceModel></span></span>  
<span data-ttu-id="9be60-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="9be60-107">\<tracking></span></span>  
<span data-ttu-id="9be60-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="9be60-108">\<profiles></span></span>  
<span data-ttu-id="9be60-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="9be60-109">\<trackingProfile></span></span>  
<span data-ttu-id="9be60-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="9be60-110">\<workflow></span></span>  
<span data-ttu-id="9be60-111">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="9be60-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="9be60-112">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="9be60-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9be60-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9be60-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9be60-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9be60-114">Attributes and elements</span></span>

<span data-ttu-id="9be60-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9be60-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9be60-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="9be60-116">Attributes</span></span>  
  
|<span data-ttu-id="9be60-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="9be60-117">Attribute</span></span>|<span data-ttu-id="9be60-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9be60-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9be60-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="9be60-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="9be60-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="9be60-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9be60-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9be60-121">Child elements</span></span>

<span data-ttu-id="9be60-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9be60-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="9be60-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9be60-123">Parent elements</span></span>
  
|<span data-ttu-id="9be60-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9be60-124">Element</span></span>|<span data-ttu-id="9be60-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="9be60-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9be60-126">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="9be60-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="9be60-127">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="9be60-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9be60-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9be60-128">See also</span></span>  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9be60-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="9be60-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9be60-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9be60-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
