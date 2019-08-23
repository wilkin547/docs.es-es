---
title: <faultPropagationQuery>de WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 6ba6478ca500c0a8ef150966a97898f8743ffdf8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925631"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="c412b-102">\<faultPropagationQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="c412b-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="c412b-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c412b-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c412b-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="c412b-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="c412b-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c412b-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="c412b-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="c412b-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="c412b-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="c412b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="c412b-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c412b-108">\<system.serviceModel></span></span>\
<span data-ttu-id="c412b-109">\<> de seguimiento </span><span class="sxs-lookup"><span data-stu-id="c412b-109">\<tracking></span></span>\
<span data-ttu-id="c412b-110">\<perfiles > </span><span class="sxs-lookup"><span data-stu-id="c412b-110">\<profiles></span></span>\
<span data-ttu-id="c412b-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c412b-111">\<trackingProfile></span></span>\
<span data-ttu-id="c412b-112">\<flujo de trabajo > </span><span class="sxs-lookup"><span data-stu-id="c412b-112">\<workflow></span></span>\
<span data-ttu-id="c412b-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c412b-113">\<faultPropagationQueries></span></span>\
<span data-ttu-id="c412b-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c412b-114">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="c412b-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c412b-115">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="c412b-116">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c412b-116">Attributes and elements</span></span>

<span data-ttu-id="c412b-117">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c412b-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c412b-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="c412b-118">Attributes</span></span>

|<span data-ttu-id="c412b-119">Atributo</span><span class="sxs-lookup"><span data-stu-id="c412b-119">Attribute</span></span>|<span data-ttu-id="c412b-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c412b-120">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="c412b-121">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="c412b-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="c412b-122">El valor predeterminado \*es, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="c412b-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="c412b-123">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="c412b-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c412b-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c412b-124">Child elements</span></span>

<span data-ttu-id="c412b-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c412b-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c412b-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c412b-126">Parent elements</span></span>

|<span data-ttu-id="c412b-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="c412b-127">Element</span></span>|<span data-ttu-id="c412b-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c412b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c412b-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c412b-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="c412b-130">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="c412b-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c412b-131">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="c412b-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c412b-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="c412b-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c412b-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c412b-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c412b-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c412b-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
