---
title: <faultPropagationQuery>de WCF
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855331"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="9ce9b-102">\<faultPropagationQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="9ce9b-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="9ce9b-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9ce9b-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="9ce9b-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="9ce9b-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="9ce9b-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="9ce9b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**  

## <a name="syntax"></a><span data-ttu-id="9ce9b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ce9b-108">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="9ce9b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ce9b-109">Attributes and elements</span></span>

<span data-ttu-id="9ce9b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="9ce9b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ce9b-111">Attributes</span></span>

|<span data-ttu-id="9ce9b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ce9b-112">Attribute</span></span>|<span data-ttu-id="9ce9b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ce9b-113">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="9ce9b-114">Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-114">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="9ce9b-115">El valor predeterminado es \* , que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-115">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="9ce9b-116">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-116">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="9ce9b-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ce9b-117">Child elements</span></span>

<span data-ttu-id="9ce9b-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-118">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9ce9b-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ce9b-119">Parent elements</span></span>

|<span data-ttu-id="9ce9b-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ce9b-120">Element</span></span>|<span data-ttu-id="9ce9b-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ce9b-121">Description</span></span>|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="9ce9b-122">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-122">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9ce9b-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="9ce9b-123">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="9ce9b-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9ce9b-124">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9ce9b-125">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9ce9b-125">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9ce9b-126">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9ce9b-126">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
