---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f3e281ff8a9de9be41dd6ad9d01ab52798d8e89e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61794555"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="81b3e-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="81b3e-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="81b3e-102">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="81b3e-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="81b3e-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="81b3e-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="81b3e-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="81b3e-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="81b3e-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="81b3e-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="81b3e-106">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="81b3e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="81b3e-107">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="81b3e-107">\<system.serviceModel>\\</span></span>
<span data-ttu-id="81b3e-108">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="81b3e-108">\<tracking>\\</span></span>
<span data-ttu-id="81b3e-109">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="81b3e-109">\<trackingProfile>\\</span></span>
<span data-ttu-id="81b3e-110">\<flujo de trabajo > \\</span><span class="sxs-lookup"><span data-stu-id="81b3e-110">\<workflow>\\</span></span>
<span data-ttu-id="81b3e-111">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="81b3e-111">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="81b3e-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="81b3e-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="81b3e-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81b3e-113">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="81b3e-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="81b3e-114">Attributes and Elements</span></span>

<span data-ttu-id="81b3e-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="81b3e-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="81b3e-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="81b3e-116">Attributes</span></span>

|<span data-ttu-id="81b3e-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="81b3e-117">Attribute</span></span>|<span data-ttu-id="81b3e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="81b3e-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="81b3e-119">activityName</span><span class="sxs-lookup"><span data-stu-id="81b3e-119">activityName</span></span>|<span data-ttu-id="81b3e-120">Una cadena que especifica el nombre de la actividad de controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="81b3e-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="81b3e-121">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="81b3e-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="81b3e-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="81b3e-122">faultHandlerActivityName</span></span>|<span data-ttu-id="81b3e-123">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="81b3e-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="81b3e-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="81b3e-124">Child Elements</span></span>

<span data-ttu-id="81b3e-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="81b3e-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="81b3e-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="81b3e-126">Parent Elements</span></span>

|<span data-ttu-id="81b3e-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="81b3e-127">Element</span></span>|<span data-ttu-id="81b3e-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="81b3e-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="81b3e-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="81b3e-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="81b3e-130">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="81b3e-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="81b3e-131">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="81b3e-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="81b3e-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="81b3e-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="81b3e-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="81b3e-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="81b3e-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="81b3e-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
