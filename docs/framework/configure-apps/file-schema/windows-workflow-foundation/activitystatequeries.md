---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 6e91078a24a950c6de027d57e3883e38f19447d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945449"
---
# <a name="activitystatequeries"></a><span data-ttu-id="a0729-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a0729-101">\<activityStateQueries></span></span>
<span data-ttu-id="a0729-102">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a0729-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="a0729-103">Por ejemplo, puede que desee realizar un seguimiento de cada vez que se complete la actividad "enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a0729-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="a0729-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="a0729-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="a0729-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="a0729-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="a0729-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a0729-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a0729-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a0729-107">\<system.serviceModel></span></span>  
<span data-ttu-id="a0729-108">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a0729-108">\<tracking></span></span>  
<span data-ttu-id="a0729-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a0729-109">\<trackingProfile></span></span>  
<span data-ttu-id="a0729-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a0729-110">\<workflow></span></span>  
<span data-ttu-id="a0729-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a0729-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0729-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a0729-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0729-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a0729-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a0729-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a0729-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0729-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="a0729-115">Attributes</span></span>  
 <span data-ttu-id="a0729-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a0729-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0729-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a0729-117">Child Elements</span></span>  
  
|<span data-ttu-id="a0729-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0729-118">Element</span></span>|<span data-ttu-id="a0729-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a0729-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0729-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="a0729-120">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="a0729-121">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="a0729-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="a0729-122">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="a0729-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0729-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a0729-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a0729-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="a0729-124">Element</span></span>|<span data-ttu-id="a0729-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="a0729-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0729-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a0729-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="a0729-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="a0729-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0729-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0729-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a0729-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="a0729-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a0729-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a0729-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
