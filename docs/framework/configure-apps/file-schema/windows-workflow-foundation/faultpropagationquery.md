---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398718"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="33b8f-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="33b8f-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="33b8f-102">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b8f-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="33b8f-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="33b8f-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="33b8f-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b8f-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="33b8f-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="33b8f-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="33b8f-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="33b8f-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="33b8f-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="33b8f-108">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="33b8f-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="33b8f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="33b8f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="33b8f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> faultPropagationQueries**](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="33b8f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="33b8f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQuery**</span><span class="sxs-lookup"><span data-stu-id="33b8f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="33b8f-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33b8f-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="33b8f-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33b8f-115">Attributes and Elements</span></span>

<span data-ttu-id="33b8f-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33b8f-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="33b8f-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="33b8f-117">Attributes</span></span>

|<span data-ttu-id="33b8f-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="33b8f-118">Attribute</span></span>|<span data-ttu-id="33b8f-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33b8f-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="33b8f-120">activityName</span><span class="sxs-lookup"><span data-stu-id="33b8f-120">activityName</span></span>|<span data-ttu-id="33b8f-121">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="33b8f-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="33b8f-122">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="33b8f-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="33b8f-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="33b8f-123">faultHandlerActivityName</span></span>|<span data-ttu-id="33b8f-124">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="33b8f-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="33b8f-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33b8f-125">Child Elements</span></span>

<span data-ttu-id="33b8f-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33b8f-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="33b8f-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33b8f-127">Parent Elements</span></span>

|<span data-ttu-id="33b8f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b8f-128">Element</span></span>|<span data-ttu-id="33b8f-129">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="33b8f-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="33b8f-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="33b8f-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="33b8f-131">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b8f-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="33b8f-132">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="33b8f-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="33b8f-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b8f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="33b8f-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="33b8f-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="33b8f-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="33b8f-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
