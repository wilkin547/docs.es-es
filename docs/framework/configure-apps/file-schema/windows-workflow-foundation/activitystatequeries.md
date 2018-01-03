---
title: '&lt;activityStateQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56845a0f596ca83f1abb31e481e38ccc3f808580
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="89b69-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="89b69-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="89b69-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89b69-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="89b69-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se completa la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89b69-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="89b69-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="89b69-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="89b69-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="89b69-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="89b69-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="89b69-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="89b69-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="89b69-108">\<system.serviceModel></span></span>  
<span data-ttu-id="89b69-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="89b69-109">\<tracking></span></span>  
<span data-ttu-id="89b69-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="89b69-110">\<trackingProfile></span></span>  
<span data-ttu-id="89b69-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="89b69-111">\<workflow></span></span>  
<span data-ttu-id="89b69-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="89b69-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b69-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89b69-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b69-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="89b69-114">Attributes and Elements</span></span>  
 <span data-ttu-id="89b69-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="89b69-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b69-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="89b69-116">Attributes</span></span>  
 <span data-ttu-id="89b69-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="89b69-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="89b69-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="89b69-118">Child Elements</span></span>  
  
|<span data-ttu-id="89b69-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="89b69-119">Element</span></span>|<span data-ttu-id="89b69-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="89b69-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b69-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="89b69-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="89b69-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="89b69-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="89b69-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="89b69-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="89b69-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="89b69-124">Parent Elements</span></span>  
  
|<span data-ttu-id="89b69-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="89b69-125">Element</span></span>|<span data-ttu-id="89b69-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="89b69-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b69-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="89b69-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="89b69-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="89b69-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="89b69-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="89b69-129">See Also</span></span>  
 <span data-ttu-id="89b69-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="89b69-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="89b69-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="89b69-131"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="89b69-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="89b69-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="89b69-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="89b69-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
