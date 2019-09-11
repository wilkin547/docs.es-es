---
title: <customTrackingQueries>de WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855440"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="ef8b9-102">\<customTrackingQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="ef8b9-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="ef8b9-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ef8b9-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="ef8b9-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ef8b9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="ef8b9-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ef8b9-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ef8b9-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ef8b9-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ef8b9-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ef8b9-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="ef8b9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="ef8b9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="ef8b9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ef8b9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="ef8b9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="ef8b9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="ef8b9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQueries**</span><span class="sxs-lookup"><span data-stu-id="ef8b9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="ef8b9-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef8b9-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef8b9-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ef8b9-114">Attributes and elements</span></span>

<span data-ttu-id="ef8b9-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef8b9-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="ef8b9-116">Attributes</span></span>

<span data-ttu-id="ef8b9-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ef8b9-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ef8b9-118">Child elements</span></span>
  
|<span data-ttu-id="ef8b9-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef8b9-119">Element</span></span>|<span data-ttu-id="ef8b9-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef8b9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef8b9-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ef8b9-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="ef8b9-122">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef8b9-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ef8b9-123">Parent elements</span></span>  
  
|<span data-ttu-id="ef8b9-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="ef8b9-124">Element</span></span>|<span data-ttu-id="ef8b9-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ef8b9-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef8b9-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ef8b9-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="ef8b9-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="ef8b9-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef8b9-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef8b9-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef8b9-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef8b9-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef8b9-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ef8b9-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
