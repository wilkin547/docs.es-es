---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9605f5d050baf046ff3c549c19191934299a65e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945753"
---
# <a name="customtrackingquery"></a><span data-ttu-id="c4c65-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c4c65-101">\<customTrackingQuery></span></span>
<span data-ttu-id="c4c65-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="c4c65-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="c4c65-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="c4c65-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="c4c65-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c4c65-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c4c65-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c4c65-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c4c65-106">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c4c65-106">\<tracking></span></span>  
<span data-ttu-id="c4c65-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c4c65-107">\<trackingProfile></span></span>  
<span data-ttu-id="c4c65-108">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c4c65-108">\<workflow></span></span>  
<span data-ttu-id="c4c65-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="c4c65-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="c4c65-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c4c65-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c65-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4c65-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4c65-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c4c65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c4c65-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c4c65-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4c65-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="c4c65-114">Attributes</span></span>  
  
|<span data-ttu-id="c4c65-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="c4c65-115">Attribute</span></span>|<span data-ttu-id="c4c65-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4c65-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4c65-117">activityName</span><span class="sxs-lookup"><span data-stu-id="c4c65-117">activityName</span></span>|<span data-ttu-id="c4c65-118">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c4c65-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="c4c65-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="c4c65-119">name</span></span>|<span data-ttu-id="c4c65-120">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="c4c65-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4c65-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c4c65-121">Child Elements</span></span>  
 <span data-ttu-id="c4c65-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c4c65-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4c65-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c4c65-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c4c65-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c4c65-124">Element</span></span>|<span data-ttu-id="c4c65-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c4c65-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4c65-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="c4c65-126">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="c4c65-127">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="c4c65-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4c65-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4c65-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c4c65-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c4c65-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c4c65-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c4c65-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
