---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 90acda7277fd276f43a619a014fbce103261aa1e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112234"
---
# <a name="activitystatequeries"></a><span data-ttu-id="132df-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="132df-101">\<activityStateQueries></span></span>
<span data-ttu-id="132df-102">Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="132df-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="132df-103">Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="132df-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="132df-104">Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.</span><span class="sxs-lookup"><span data-stu-id="132df-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="132df-105">Los estados de suscripción disponibles se especifican en ActivityStates.</span><span class="sxs-lookup"><span data-stu-id="132df-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="132df-106">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="132df-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="132df-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="132df-107">\<system.serviceModel></span></span>  
<span data-ttu-id="132df-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="132df-108">\<tracking></span></span>  
<span data-ttu-id="132df-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="132df-109">\<trackingProfile></span></span>  
<span data-ttu-id="132df-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="132df-110">\<workflow></span></span>  
<span data-ttu-id="132df-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="132df-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="132df-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="132df-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="132df-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="132df-113">Attributes and Elements</span></span>  
 <span data-ttu-id="132df-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="132df-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="132df-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="132df-115">Attributes</span></span>  
 <span data-ttu-id="132df-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="132df-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="132df-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="132df-117">Child Elements</span></span>  
  
|<span data-ttu-id="132df-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="132df-118">Element</span></span>|<span data-ttu-id="132df-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="132df-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132df-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="132df-120">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="132df-121">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="132df-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="132df-122">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="132df-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="132df-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="132df-123">Parent Elements</span></span>  
  
|<span data-ttu-id="132df-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="132df-124">Element</span></span>|<span data-ttu-id="132df-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="132df-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="132df-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="132df-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="132df-127">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="132df-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="132df-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="132df-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="132df-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="132df-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="132df-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="132df-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
