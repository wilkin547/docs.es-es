---
title: <faultPropagationQuery>de WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855331"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="13e6b-102">\<faultPropagationQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="13e6b-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="13e6b-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="13e6b-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="13e6b-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="13e6b-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="13e6b-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="13e6b-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="13e6b-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="13e6b-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="13e6b-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="13e6b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="13e6b-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13e6b-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="13e6b-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="13e6b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="13e6b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="13e6b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="13e6b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="13e6b-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> faultPropagationQueries**](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="13e6b-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="13e6b-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQuery**</span><span class="sxs-lookup"><span data-stu-id="13e6b-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="13e6b-116">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13e6b-116">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="13e6b-117">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="13e6b-117">Attributes and elements</span></span>

<span data-ttu-id="13e6b-118">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="13e6b-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="13e6b-119">Atributos</span><span class="sxs-lookup"><span data-stu-id="13e6b-119">Attributes</span></span>

|<span data-ttu-id="13e6b-120">Atributo</span><span class="sxs-lookup"><span data-stu-id="13e6b-120">Attribute</span></span>|<span data-ttu-id="13e6b-121">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="13e6b-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="13e6b-122">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="13e6b-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="13e6b-123">El valor predeterminado \*es, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="13e6b-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="13e6b-124">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="13e6b-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="13e6b-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="13e6b-125">Child elements</span></span>

<span data-ttu-id="13e6b-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="13e6b-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="13e6b-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="13e6b-127">Parent elements</span></span>

|<span data-ttu-id="13e6b-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="13e6b-128">Element</span></span>|<span data-ttu-id="13e6b-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="13e6b-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="13e6b-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="13e6b-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="13e6b-131">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="13e6b-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="13e6b-132">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="13e6b-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="13e6b-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="13e6b-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="13e6b-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="13e6b-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="13e6b-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="13e6b-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
