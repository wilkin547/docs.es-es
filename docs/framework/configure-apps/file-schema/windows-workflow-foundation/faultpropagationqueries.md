---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: b8052138a729fcba7cb158d81a63126f59e0c4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69988737"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="5f494-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="5f494-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="5f494-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="5f494-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5f494-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="5f494-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="5f494-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="5f494-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="5f494-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="5f494-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="5f494-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5f494-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5f494-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5f494-107">\<system.serviceModel></span></span>  
<span data-ttu-id="5f494-108">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5f494-108">\<tracking></span></span>  
<span data-ttu-id="5f494-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5f494-109">\<trackingProfile></span></span>  
<span data-ttu-id="5f494-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f494-110">\<workflow></span></span>  
<span data-ttu-id="5f494-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="5f494-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f494-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f494-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f494-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5f494-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5f494-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5f494-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f494-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5f494-115">Attributes</span></span>  
 <span data-ttu-id="5f494-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5f494-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5f494-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5f494-117">Child Elements</span></span>  
  
|<span data-ttu-id="5f494-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f494-118">Element</span></span>|<span data-ttu-id="5f494-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5f494-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f494-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="5f494-120">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="5f494-121">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="5f494-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="5f494-122">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="5f494-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5f494-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5f494-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5f494-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="5f494-124">Element</span></span>|<span data-ttu-id="5f494-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5f494-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f494-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5f494-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="5f494-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="5f494-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f494-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f494-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5f494-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5f494-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5f494-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5f494-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
