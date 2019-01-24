---
title: '&lt;activityStateQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: bfd19e00e79a95eb717ca9131e92b5ff5c600d5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511987"
---
# <a name="ltactivitystatequeriesgt"></a><span data-ttu-id="6db00-102">&lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6db00-102">&lt;activityStateQueries&gt;</span></span>
<span data-ttu-id="6db00-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6db00-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="6db00-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6db00-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="6db00-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="6db00-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="6db00-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="6db00-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="6db00-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="6db00-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6db00-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6db00-108">\<system.serviceModel></span></span>  
<span data-ttu-id="6db00-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6db00-109">\<tracking></span></span>  
<span data-ttu-id="6db00-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6db00-110">\<trackingProfile></span></span>  
<span data-ttu-id="6db00-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="6db00-111">\<workflow></span></span>  
<span data-ttu-id="6db00-112">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6db00-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6db00-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6db00-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6db00-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6db00-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6db00-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6db00-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6db00-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="6db00-116">Attributes</span></span>  
 <span data-ttu-id="6db00-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6db00-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6db00-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6db00-118">Child Elements</span></span>  
  
|<span data-ttu-id="6db00-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6db00-119">Element</span></span>|<span data-ttu-id="6db00-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6db00-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6db00-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6db00-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="6db00-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="6db00-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="6db00-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="6db00-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6db00-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6db00-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6db00-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6db00-125">Element</span></span>|<span data-ttu-id="6db00-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="6db00-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6db00-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6db00-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6db00-128">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="6db00-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6db00-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="6db00-129">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6db00-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="6db00-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6db00-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6db00-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
