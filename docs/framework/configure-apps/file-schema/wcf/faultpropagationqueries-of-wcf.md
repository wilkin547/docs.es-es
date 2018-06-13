---
title: '&lt;faultPropagationQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 5db043b5d4d150628df386dafb6e7bd351a0a28a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754010"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="3b42f-102">&lt;faultPropagationQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="3b42f-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="3b42f-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3b42f-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3b42f-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="3b42f-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3b42f-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3b42f-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3b42f-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="3b42f-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="3b42f-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3b42f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="3b42f-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3b42f-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3b42f-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="3b42f-109">\<tracking></span></span>  
<span data-ttu-id="3b42f-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3b42f-110">\<trackingProfile></span></span>  
<span data-ttu-id="3b42f-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3b42f-111">\<workflow></span></span>  
<span data-ttu-id="3b42f-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3b42f-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b42f-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b42f-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3b42f-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3b42f-114">Attributes and Elements</span></span>  
 <span data-ttu-id="3b42f-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3b42f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b42f-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="3b42f-116">Attributes</span></span>  
 <span data-ttu-id="3b42f-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3b42f-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3b42f-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3b42f-118">Child Elements</span></span>  
  
|<span data-ttu-id="3b42f-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b42f-119">Element</span></span>|<span data-ttu-id="3b42f-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b42f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b42f-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3b42f-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="3b42f-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="3b42f-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3b42f-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="3b42f-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b42f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3b42f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3b42f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3b42f-125">Element</span></span>|<span data-ttu-id="3b42f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b42f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b42f-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="3b42f-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="3b42f-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="3b42f-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b42f-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b42f-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="3b42f-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3b42f-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3b42f-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3b42f-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
