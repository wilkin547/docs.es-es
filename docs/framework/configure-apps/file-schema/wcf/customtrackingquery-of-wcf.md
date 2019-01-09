---
title: '&lt;customTrackingQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 234703e677f838dcdccdf857ba38b8729d25a488
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146386"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="fb840-102">&lt;customTrackingQuery&gt; de WCF</span><span class="sxs-lookup"><span data-stu-id="fb840-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="fb840-103">Representa una consulta que se usa para realizar un seguimiento de eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="fb840-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="fb840-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="fb840-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="fb840-105">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="fb840-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="fb840-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fb840-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fb840-107">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="fb840-107">\<tracking></span></span>  
<span data-ttu-id="fb840-108">\<perfiles de ></span><span class="sxs-lookup"><span data-stu-id="fb840-108">\<profiles></span></span>  
<span data-ttu-id="fb840-109">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="fb840-109">\<trackingProfile></span></span>  
<span data-ttu-id="fb840-110">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="fb840-110">\<workflow></span></span>  
<span data-ttu-id="fb840-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="fb840-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="fb840-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="fb840-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb840-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb840-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fb840-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fb840-114">Attributes and elements</span></span>  

<span data-ttu-id="fb840-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fb840-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fb840-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="fb840-116">Attributes</span></span>  
  
|<span data-ttu-id="fb840-117">Atributo</span><span class="sxs-lookup"><span data-stu-id="fb840-117">Attribute</span></span>|<span data-ttu-id="fb840-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb840-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="fb840-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fb840-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="fb840-120">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="fb840-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fb840-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fb840-121">Child elements</span></span>

<span data-ttu-id="fb840-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fb840-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="fb840-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fb840-123">Parent elements</span></span>

|<span data-ttu-id="fb840-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="fb840-124">Element</span></span>|<span data-ttu-id="fb840-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb840-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fb840-126">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="fb840-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="fb840-127">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="fb840-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="fb840-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb840-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="fb840-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="fb840-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fb840-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fb840-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
