---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790226"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="b3f07-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="b3f07-101">\<customTrackingQueries></span></span>
<span data-ttu-id="b3f07-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="b3f07-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="b3f07-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="b3f07-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="b3f07-104">Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b3f07-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b3f07-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b3f07-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b3f07-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b3f07-106">\<tracking></span></span>  
<span data-ttu-id="b3f07-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b3f07-107">\<trackingProfile></span></span>  
<span data-ttu-id="b3f07-108">\<flujo de trabajo ></span><span class="sxs-lookup"><span data-stu-id="b3f07-108">\<workflow></span></span>  
<span data-ttu-id="b3f07-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="b3f07-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f07-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3f07-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3f07-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b3f07-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b3f07-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b3f07-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3f07-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b3f07-113">Attributes</span></span>  
 <span data-ttu-id="b3f07-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b3f07-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b3f07-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b3f07-115">Child Elements</span></span>  
  
|<span data-ttu-id="b3f07-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3f07-116">Element</span></span>|<span data-ttu-id="b3f07-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3f07-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3f07-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="b3f07-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="b3f07-119">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="b3f07-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3f07-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b3f07-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b3f07-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b3f07-121">Element</span></span>|<span data-ttu-id="b3f07-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3f07-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3f07-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b3f07-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b3f07-124">Un elemento de configuración que contiene todas las consultas de un flujo de trabajo concreto identificado por el **activityDefinitionId** propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3f07-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3f07-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3f07-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b3f07-126">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b3f07-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b3f07-127">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b3f07-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
