---
title: <customTrackingQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919359"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="f0b47-102">\<customTrackingQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="f0b47-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="f0b47-103">Representa una consulta que se usa para realizar el seguimiento de los eventos que se definen en las actividades de código.</span><span class="sxs-lookup"><span data-stu-id="f0b47-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="f0b47-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="f0b47-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="f0b47-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="f0b47-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f0b47-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f0b47-106">\<system.serviceModel></span></span>  
<span data-ttu-id="f0b47-107">\<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f0b47-107">\<tracking></span></span>  
<span data-ttu-id="f0b47-108">\<perfiles ></span><span class="sxs-lookup"><span data-stu-id="f0b47-108">\<profiles></span></span>  
<span data-ttu-id="f0b47-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f0b47-109">\<trackingProfile></span></span>  
<span data-ttu-id="f0b47-110">\<> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f0b47-110">\<workflow></span></span>  
<span data-ttu-id="f0b47-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="f0b47-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="f0b47-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f0b47-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b47-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f0b47-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0b47-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f0b47-114">Attributes and elements</span></span>  

<span data-ttu-id="f0b47-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f0b47-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0b47-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="f0b47-116">Attributes</span></span>  
  
|<span data-ttu-id="f0b47-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="f0b47-117">Attribute</span></span>|<span data-ttu-id="f0b47-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0b47-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="f0b47-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f0b47-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="f0b47-120">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="f0b47-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0b47-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f0b47-121">Child elements</span></span>

<span data-ttu-id="f0b47-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f0b47-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="f0b47-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f0b47-123">Parent elements</span></span>

|<span data-ttu-id="f0b47-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="f0b47-124">Element</span></span>|<span data-ttu-id="f0b47-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f0b47-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0b47-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="f0b47-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="f0b47-127">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="f0b47-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="f0b47-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="f0b47-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f0b47-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="f0b47-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f0b47-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f0b47-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
