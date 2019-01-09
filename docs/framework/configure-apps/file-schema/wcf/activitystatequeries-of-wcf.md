---
title: '&lt;activityStateQueries&gt; de WCF'
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 2dabfdd248006de60b5e84e739f78e03f364dde3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146191"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="53a64-102">&lt;activityStateQueries&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="53a64-102">&lt;activityStateQueries&gt; of WCF</span></span>

<span data-ttu-id="53a64-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53a64-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="53a64-104">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53a64-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="53a64-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="53a64-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="53a64-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="53a64-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="53a64-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="53a64-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="53a64-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="53a64-108">\<system.serviceModel></span></span>  
<span data-ttu-id="53a64-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="53a64-109">\<tracking></span></span>  
<span data-ttu-id="53a64-110">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="53a64-110">\<profiles></span></span>  
<span data-ttu-id="53a64-111">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="53a64-111">\<trackingProfile></span></span>  
<span data-ttu-id="53a64-112">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="53a64-112">\<workflow></span></span>  
<span data-ttu-id="53a64-113">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="53a64-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="53a64-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53a64-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  

## <a name="attributes-and-elements"></a><span data-ttu-id="53a64-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53a64-115">Attributes and elements</span></span>

<span data-ttu-id="53a64-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53a64-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="53a64-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="53a64-117">Attributes</span></span>  

<span data-ttu-id="53a64-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="53a64-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="53a64-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53a64-119">Child elements</span></span>

|<span data-ttu-id="53a64-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="53a64-120">Element</span></span>|<span data-ttu-id="53a64-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="53a64-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53a64-122">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="53a64-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="53a64-123">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="53a64-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="53a64-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="53a64-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="53a64-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53a64-125">Parent elements</span></span>

|<span data-ttu-id="53a64-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="53a64-126">Element</span></span>|<span data-ttu-id="53a64-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="53a64-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="53a64-128">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="53a64-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="53a64-129">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="53a64-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="53a64-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="53a64-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [<span data-ttu-id="53a64-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="53a64-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="53a64-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="53a64-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
