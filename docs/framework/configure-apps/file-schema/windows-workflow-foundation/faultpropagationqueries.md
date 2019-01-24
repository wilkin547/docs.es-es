---
title: '&lt;faultPropagationQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 546b37279c8ba58f9dd9f07dabacb7af602ff232
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610063"
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="24629-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="24629-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="24629-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="24629-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="24629-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="24629-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="24629-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="24629-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="24629-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="24629-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="24629-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="24629-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="24629-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="24629-108">\<system.serviceModel></span></span>  
<span data-ttu-id="24629-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="24629-109">\<tracking></span></span>  
<span data-ttu-id="24629-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="24629-110">\<trackingProfile></span></span>  
<span data-ttu-id="24629-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="24629-111">\<workflow></span></span>  
<span data-ttu-id="24629-112">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="24629-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24629-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24629-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24629-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="24629-114">Attributes and Elements</span></span>  
 <span data-ttu-id="24629-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="24629-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24629-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="24629-116">Attributes</span></span>  
 <span data-ttu-id="24629-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="24629-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24629-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="24629-118">Child Elements</span></span>  
  
|<span data-ttu-id="24629-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="24629-119">Element</span></span>|<span data-ttu-id="24629-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="24629-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24629-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="24629-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="24629-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="24629-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="24629-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="24629-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24629-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24629-124">Parent Elements</span></span>  
  
|<span data-ttu-id="24629-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="24629-125">Element</span></span>|<span data-ttu-id="24629-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="24629-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24629-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="24629-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="24629-128">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="24629-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="24629-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="24629-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="24629-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="24629-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="24629-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="24629-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
