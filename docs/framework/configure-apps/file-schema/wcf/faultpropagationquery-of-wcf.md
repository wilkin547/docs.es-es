---
title: <faultPropagationQuery> de WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: e5793852d49a052d05f6cb2f4efbe166d67afc62
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675412"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="d201a-102">\<faultPropagationQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="d201a-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="d201a-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="d201a-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d201a-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="d201a-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d201a-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="d201a-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d201a-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="d201a-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="d201a-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d201a-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="d201a-108">\<system.serviceModel>\\</span><span class="sxs-lookup"><span data-stu-id="d201a-108">\<system.serviceModel>\\</span></span>
<span data-ttu-id="d201a-109">\<tracking>\\</span><span class="sxs-lookup"><span data-stu-id="d201a-109">\<tracking>\\</span></span>
<span data-ttu-id="d201a-110">\<perfiles > \\</span><span class="sxs-lookup"><span data-stu-id="d201a-110">\<profiles>\\</span></span>
<span data-ttu-id="d201a-111">\<trackingProfile>\\</span><span class="sxs-lookup"><span data-stu-id="d201a-111">\<trackingProfile>\\</span></span>
<span data-ttu-id="d201a-112">\<flujo de trabajo > \\</span><span class="sxs-lookup"><span data-stu-id="d201a-112">\<workflow>\\</span></span>
<span data-ttu-id="d201a-113">\<faultPropagationQueries>\\</span><span class="sxs-lookup"><span data-stu-id="d201a-113">\<faultPropagationQueries>\\</span></span>
<span data-ttu-id="d201a-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="d201a-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="d201a-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d201a-115">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d201a-116">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d201a-116">Attributes and elements</span></span>

<span data-ttu-id="d201a-117">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d201a-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d201a-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="d201a-118">Attributes</span></span>

|<span data-ttu-id="d201a-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="d201a-119">Attribute</span></span>|<span data-ttu-id="d201a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="d201a-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="d201a-121">Una cadena que especifica el nombre de la actividad de controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="d201a-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="d201a-122">El valor predeterminado es \*, lo que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="d201a-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="d201a-123">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="d201a-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d201a-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d201a-124">Child elements</span></span>

<span data-ttu-id="d201a-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d201a-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d201a-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d201a-126">Parent elements</span></span>

|<span data-ttu-id="d201a-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="d201a-127">Element</span></span>|<span data-ttu-id="d201a-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="d201a-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d201a-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="d201a-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="d201a-130">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="d201a-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d201a-131">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="d201a-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="d201a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="d201a-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d201a-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d201a-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d201a-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d201a-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
