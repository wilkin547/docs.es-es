---
title: <cancelRequestedQuery>de WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 7952520edbf799e5fab6864e50962c6ec2860928
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919644"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="d03a5-102">\<cancelRequestedQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="d03a5-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="d03a5-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d03a5-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d03a5-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="d03a5-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="d03a5-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d03a5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="d03a5-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d03a5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d03a5-107">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d03a5-107">\<tracking></span></span>  
<span data-ttu-id="d03a5-108">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="d03a5-108">\<profiles></span></span>  
<span data-ttu-id="d03a5-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d03a5-109">\<trackingProfile></span></span>  
<span data-ttu-id="d03a5-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d03a5-110">\<workflow></span></span>  
<span data-ttu-id="d03a5-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d03a5-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="d03a5-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d03a5-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d03a5-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d03a5-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d03a5-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d03a5-114">Attributes and elements</span></span>

<span data-ttu-id="d03a5-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d03a5-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d03a5-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="d03a5-116">Attributes</span></span>  
  
|<span data-ttu-id="d03a5-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="d03a5-117">Attribute</span></span>|<span data-ttu-id="d03a5-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d03a5-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d03a5-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="d03a5-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="d03a5-120">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="d03a5-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d03a5-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d03a5-121">Child elements</span></span>

<span data-ttu-id="d03a5-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d03a5-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="d03a5-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d03a5-123">Parent elements</span></span>
  
|<span data-ttu-id="d03a5-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="d03a5-124">Element</span></span>|<span data-ttu-id="d03a5-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d03a5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d03a5-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d03a5-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="d03a5-127">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="d03a5-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d03a5-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="d03a5-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d03a5-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d03a5-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d03a5-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d03a5-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
