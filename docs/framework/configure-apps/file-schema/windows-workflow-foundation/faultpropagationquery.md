---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398718"
---
# \<faultPropagationQuery>

<span data-ttu-id="82bf7-101">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="82bf7-101">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="82bf7-102">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="82bf7-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="82bf7-103">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="82bf7-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="82bf7-104">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="82bf7-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="82bf7-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="82bf7-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a><span data-ttu-id="82bf7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="82bf7-106">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="82bf7-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="82bf7-107">Attributes and Elements</span></span>

<span data-ttu-id="82bf7-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="82bf7-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="82bf7-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="82bf7-109">Attributes</span></span>

|<span data-ttu-id="82bf7-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="82bf7-110">Attribute</span></span>|<span data-ttu-id="82bf7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="82bf7-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="82bf7-112">activityName</span><span class="sxs-lookup"><span data-stu-id="82bf7-112">activityName</span></span>|<span data-ttu-id="82bf7-113">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="82bf7-113">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="82bf7-114">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="82bf7-114">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="82bf7-115">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="82bf7-115">faultHandlerActivityName</span></span>|<span data-ttu-id="82bf7-116">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="82bf7-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="82bf7-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="82bf7-117">Child Elements</span></span>

<span data-ttu-id="82bf7-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="82bf7-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="82bf7-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="82bf7-119">Parent Elements</span></span>

|<span data-ttu-id="82bf7-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="82bf7-120">Element</span></span>|<span data-ttu-id="82bf7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="82bf7-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|<span data-ttu-id="82bf7-122">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="82bf7-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="82bf7-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="82bf7-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="82bf7-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="82bf7-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="82bf7-125">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="82bf7-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="82bf7-126">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="82bf7-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
