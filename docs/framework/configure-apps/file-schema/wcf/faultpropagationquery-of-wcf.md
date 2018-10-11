---
title: '&lt;faultPropagationQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: df7119363e94a070bb898c984c12cf82755c3407
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087705"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="1791c-102">&lt;faultPropagationQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="1791c-102">&lt;faultPropagationQuery&gt; of WCF</span></span>
<span data-ttu-id="1791c-103">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1791c-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1791c-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="1791c-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1791c-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1791c-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1791c-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="1791c-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="1791c-107">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="1791c-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="1791c-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1791c-108">\<system.serviceModel></span></span>  
<span data-ttu-id="1791c-109">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1791c-109">\<tracking></span></span>  
<span data-ttu-id="1791c-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="1791c-110">\<trackingProfile></span></span>  
<span data-ttu-id="1791c-111">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="1791c-111">\<workflow></span></span>  
<span data-ttu-id="1791c-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="1791c-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="1791c-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="1791c-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1791c-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1791c-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String"/>
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1791c-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1791c-115">Attributes and Elements</span></span>  
 <span data-ttu-id="1791c-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1791c-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1791c-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="1791c-117">Attributes</span></span>  
  
|<span data-ttu-id="1791c-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="1791c-118">Attribute</span></span>|<span data-ttu-id="1791c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="1791c-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1791c-120">activityName</span><span class="sxs-lookup"><span data-stu-id="1791c-120">activityName</span></span>|<span data-ttu-id="1791c-121">Una cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="1791c-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="1791c-122">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="1791c-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="1791c-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="1791c-123">faultHandlerActivityName</span></span>|<span data-ttu-id="1791c-124">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="1791c-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1791c-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1791c-125">Child Elements</span></span>  
 <span data-ttu-id="1791c-126">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1791c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1791c-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1791c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1791c-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="1791c-128">Element</span></span>|<span data-ttu-id="1791c-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="1791c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1791c-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1791c-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="1791c-131">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="1791c-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1791c-132">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="1791c-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1791c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1791c-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="1791c-134">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="1791c-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1791c-135">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1791c-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
