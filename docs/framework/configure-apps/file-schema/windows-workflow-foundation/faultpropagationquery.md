---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 1a6899eaa04ad16192e07f4bc2ad1abe6e4aedd5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257374"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="dddc7-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="dddc7-101">\<faultPropagationQuery></span></span>
<span data-ttu-id="dddc7-102">Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dddc7-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dddc7-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="dddc7-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="dddc7-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dddc7-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="dddc7-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="dddc7-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="dddc7-106">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dddc7-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dddc7-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="dddc7-107">\<system.serviceModel></span></span>  
<span data-ttu-id="dddc7-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="dddc7-108">\<tracking></span></span>  
<span data-ttu-id="dddc7-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="dddc7-109">\<trackingProfile></span></span>  
<span data-ttu-id="dddc7-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="dddc7-110">\<workflow></span></span>  
<span data-ttu-id="dddc7-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="dddc7-111">\<faultPropagationQueries></span></span>  
<span data-ttu-id="dddc7-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="dddc7-112">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dddc7-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dddc7-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dddc7-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dddc7-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dddc7-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dddc7-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dddc7-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="dddc7-116">Attributes</span></span>  
  
|<span data-ttu-id="dddc7-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="dddc7-117">Attribute</span></span>|<span data-ttu-id="dddc7-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="dddc7-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dddc7-119">activityName</span><span class="sxs-lookup"><span data-stu-id="dddc7-119">activityName</span></span>|<span data-ttu-id="dddc7-120">Una cadena que especifica el nombre de la actividad del controlador de errores que propagó el error.</span><span class="sxs-lookup"><span data-stu-id="dddc7-120">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="dddc7-121">El valor predeterminado es \*, que indica que los registros de propagación de errores se devuelven para todas las actividades.</span><span class="sxs-lookup"><span data-stu-id="dddc7-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="dddc7-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="dddc7-122">faultHandlerActivityName</span></span>|<span data-ttu-id="dddc7-123">Una cadena que especifica el nombre de la actividad que originó el error.</span><span class="sxs-lookup"><span data-stu-id="dddc7-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dddc7-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dddc7-124">Child Elements</span></span>  
 <span data-ttu-id="dddc7-125">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dddc7-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dddc7-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dddc7-126">Parent Elements</span></span>  
  
|<span data-ttu-id="dddc7-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="dddc7-127">Element</span></span>|<span data-ttu-id="dddc7-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="dddc7-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dddc7-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="dddc7-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="dddc7-130">Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dddc7-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dddc7-131">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="dddc7-131">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dddc7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="dddc7-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dddc7-133">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dddc7-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dddc7-134">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dddc7-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
