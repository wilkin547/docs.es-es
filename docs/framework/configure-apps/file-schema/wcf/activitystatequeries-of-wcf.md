---
title: '&lt;activityStateQueries&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: b2685da4d5ede9f3d880f6627e86db79b57ee395
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="97f67-102">&lt;activityStateQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="97f67-102">&lt;activityStateQueries&gt; of WCF</span></span>
<span data-ttu-id="97f67-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97f67-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="97f67-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se completa la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="97f67-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="97f67-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="97f67-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="97f67-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="97f67-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="97f67-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="97f67-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="97f67-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="97f67-108">\<system.serviceModel></span></span>  
<span data-ttu-id="97f67-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="97f67-109">\<tracking></span></span>  
<span data-ttu-id="97f67-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="97f67-110">\<trackingProfile></span></span>  
<span data-ttu-id="97f67-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="97f67-111">\<workflow></span></span>  
<span data-ttu-id="97f67-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="97f67-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97f67-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97f67-113">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97f67-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="97f67-114">Attributes and Elements</span></span>  
 <span data-ttu-id="97f67-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="97f67-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97f67-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="97f67-116">Attributes</span></span>  
 <span data-ttu-id="97f67-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="97f67-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97f67-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="97f67-118">Child Elements</span></span>  
  
|<span data-ttu-id="97f67-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="97f67-119">Element</span></span>|<span data-ttu-id="97f67-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="97f67-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97f67-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="97f67-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="97f67-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="97f67-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="97f67-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="97f67-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97f67-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="97f67-124">Parent Elements</span></span>  
  
|<span data-ttu-id="97f67-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="97f67-125">Element</span></span>|<span data-ttu-id="97f67-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="97f67-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97f67-127">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="97f67-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="97f67-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="97f67-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97f67-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="97f67-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
 <xref:System.Activities.Tracking.ActivityStateQuery>    
 [<span data-ttu-id="97f67-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="97f67-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="97f67-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="97f67-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
