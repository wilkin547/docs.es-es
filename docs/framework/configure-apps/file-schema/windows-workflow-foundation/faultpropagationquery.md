---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f77a613f4eb0456a0085096aa478d37c78122217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946313"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="0f6f8-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="0f6f8-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="0f6f8-102">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0f6f8-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="0f6f8-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="0f6f8-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="0f6f8-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="0f6f8-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="0f6f8-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0f6f8-107">\<system.serviceModel></span></span>\
<span data-ttu-id="0f6f8-108">\<> de seguimiento </span><span class="sxs-lookup"><span data-stu-id="0f6f8-108">\<tracking></span></span>\
<span data-ttu-id="0f6f8-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0f6f8-109">\<trackingProfile></span></span>\
<span data-ttu-id="0f6f8-110">\<flujo de trabajo > </span><span class="sxs-lookup"><span data-stu-id="0f6f8-110">\<workflow></span></span>\
<span data-ttu-id="0f6f8-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="0f6f8-111">\<faultPropagationQueries></span></span>\
<span data-ttu-id="0f6f8-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="0f6f8-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="0f6f8-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f6f8-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="0f6f8-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0f6f8-114">Attributes and Elements</span></span>

<span data-ttu-id="0f6f8-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="0f6f8-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="0f6f8-116">Attributes</span></span>

|<span data-ttu-id="0f6f8-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="0f6f8-117">Attribute</span></span>|<span data-ttu-id="0f6f8-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f6f8-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="0f6f8-119">activityName</span><span class="sxs-lookup"><span data-stu-id="0f6f8-119">activityName</span></span>|<span data-ttu-id="0f6f8-120">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="0f6f8-121">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="0f6f8-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="0f6f8-122">faultHandlerActivityName</span></span>|<span data-ttu-id="0f6f8-123">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="0f6f8-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0f6f8-124">Child Elements</span></span>

<span data-ttu-id="0f6f8-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0f6f8-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0f6f8-126">Parent Elements</span></span>

|<span data-ttu-id="0f6f8-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="0f6f8-127">Element</span></span>|<span data-ttu-id="0f6f8-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="0f6f8-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="0f6f8-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="0f6f8-129">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="0f6f8-130">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0f6f8-131">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="0f6f8-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="0f6f8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f6f8-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0f6f8-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0f6f8-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0f6f8-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0f6f8-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
