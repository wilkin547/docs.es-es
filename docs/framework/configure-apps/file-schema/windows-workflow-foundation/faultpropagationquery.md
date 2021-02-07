---
description: 'Más información acerca de: <faultPropagationQuery>'
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 08786bfa66d74f5f29353c4d6a86a2abd34df8f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748705"
---
# \<faultPropagationQuery>

<span data-ttu-id="2727e-102">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="2727e-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2727e-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="2727e-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="2727e-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="2727e-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="2727e-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="2727e-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="2727e-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="2727e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="2727e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2727e-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="2727e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2727e-108">Attributes and Elements</span></span>

<span data-ttu-id="2727e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2727e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="2727e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="2727e-110">Attributes</span></span>

|<span data-ttu-id="2727e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="2727e-111">Attribute</span></span>|<span data-ttu-id="2727e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="2727e-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="2727e-113">activityName</span><span class="sxs-lookup"><span data-stu-id="2727e-113">activityName</span></span>|<span data-ttu-id="2727e-114">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="2727e-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="2727e-115">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="2727e-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="2727e-116">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="2727e-116">faultHandlerActivityName</span></span>|<span data-ttu-id="2727e-117">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="2727e-117">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="2727e-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2727e-118">Child Elements</span></span>

<span data-ttu-id="2727e-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2727e-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="2727e-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2727e-120">Parent Elements</span></span>

|<span data-ttu-id="2727e-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="2727e-121">Element</span></span>|<span data-ttu-id="2727e-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2727e-122">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="2727e-123">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="2727e-123">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="2727e-124">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="2727e-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="2727e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2727e-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2727e-126">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2727e-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2727e-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2727e-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
