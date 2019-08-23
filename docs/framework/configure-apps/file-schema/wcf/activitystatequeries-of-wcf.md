---
title: <activityStateQueries>de WCF
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920295"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="b1aeb-102">\<activityStateQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="b1aeb-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="b1aeb-103">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="b1aeb-104">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="b1aeb-105">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="b1aeb-106">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="b1aeb-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b1aeb-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="b1aeb-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b1aeb-108">\<system.serviceModel></span></span>  
<span data-ttu-id="b1aeb-109">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b1aeb-109">\<tracking></span></span>  
<span data-ttu-id="b1aeb-110">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="b1aeb-110">\<profiles></span></span>  
<span data-ttu-id="b1aeb-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b1aeb-111">\<trackingProfile></span></span>  
<span data-ttu-id="b1aeb-112">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b1aeb-112">\<workflow></span></span>  
<span data-ttu-id="b1aeb-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b1aeb-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="b1aeb-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1aeb-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="b1aeb-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b1aeb-115">Attributes and elements</span></span>

<span data-ttu-id="b1aeb-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b1aeb-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="b1aeb-117">Attributes</span></span>  

<span data-ttu-id="b1aeb-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="b1aeb-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b1aeb-119">Child elements</span></span>

|<span data-ttu-id="b1aeb-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1aeb-120">Element</span></span>|<span data-ttu-id="b1aeb-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b1aeb-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1aeb-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b1aeb-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="b1aeb-123">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b1aeb-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b1aeb-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b1aeb-125">Parent elements</span></span>

|<span data-ttu-id="b1aeb-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b1aeb-126">Element</span></span>|<span data-ttu-id="b1aeb-127">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b1aeb-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b1aeb-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b1aeb-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b1aeb-129">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="b1aeb-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b1aeb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1aeb-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="b1aeb-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b1aeb-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b1aeb-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b1aeb-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
