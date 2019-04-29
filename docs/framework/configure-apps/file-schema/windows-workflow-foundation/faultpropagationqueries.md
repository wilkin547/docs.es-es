---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790161"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="691d7-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="691d7-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="691d7-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="691d7-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="691d7-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="691d7-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="691d7-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="691d7-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="691d7-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="691d7-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="691d7-106">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="691d7-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="691d7-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="691d7-107">\<system.serviceModel></span></span>  
<span data-ttu-id="691d7-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="691d7-108">\<tracking></span></span>  
<span data-ttu-id="691d7-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="691d7-109">\<trackingProfile></span></span>  
<span data-ttu-id="691d7-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="691d7-110">\<workflow></span></span>  
<span data-ttu-id="691d7-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="691d7-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="691d7-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="691d7-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="691d7-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="691d7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="691d7-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="691d7-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="691d7-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="691d7-115">Attributes</span></span>  
 <span data-ttu-id="691d7-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="691d7-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="691d7-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="691d7-117">Child Elements</span></span>  
  
|<span data-ttu-id="691d7-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="691d7-118">Element</span></span>|<span data-ttu-id="691d7-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="691d7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="691d7-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="691d7-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="691d7-121">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="691d7-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="691d7-122">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="691d7-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="691d7-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="691d7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="691d7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="691d7-124">Element</span></span>|<span data-ttu-id="691d7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="691d7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="691d7-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="691d7-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="691d7-127">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="691d7-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="691d7-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="691d7-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="691d7-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="691d7-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="691d7-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="691d7-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
