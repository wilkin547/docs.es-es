---
description: 'Más información sobre: <faultPropagationQuery> de WCF'
title: <faultPropagationQuery> de WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: cd26bf76fec54371ef0455b93c98650bdab19068
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782070"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="910d3-103">\<faultPropagationQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="910d3-103">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="910d3-104">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="910d3-104">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="910d3-105">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="910d3-105">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="910d3-106">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="910d3-106">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="910d3-107">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="910d3-107">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="910d3-108">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="910d3-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="910d3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="910d3-109">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="910d3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="910d3-110">Attributes and elements</span></span>

<span data-ttu-id="910d3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="910d3-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="910d3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="910d3-112">Attributes</span></span>

|<span data-ttu-id="910d3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="910d3-113">Attribute</span></span>|<span data-ttu-id="910d3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="910d3-114">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="910d3-115">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="910d3-115">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="910d3-116">El valor predeterminado es \* , que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="910d3-116">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="910d3-117">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="910d3-117">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="910d3-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="910d3-118">Child elements</span></span>

<span data-ttu-id="910d3-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="910d3-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="910d3-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="910d3-120">Parent elements</span></span>

|<span data-ttu-id="910d3-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="910d3-121">Element</span></span>|<span data-ttu-id="910d3-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="910d3-122">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="910d3-123">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="910d3-123">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="910d3-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="910d3-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="910d3-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="910d3-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="910d3-126">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="910d3-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="910d3-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="910d3-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
