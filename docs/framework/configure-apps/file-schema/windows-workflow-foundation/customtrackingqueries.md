---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 398b018ce407aee0687c95037753f3affa07aa9b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398780"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="5197d-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5197d-101">\<customTrackingQueries></span></span>
<span data-ttu-id="5197d-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="5197d-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5197d-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="5197d-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5197d-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="5197d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5197d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5197d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5197d-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5197d-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5197d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5197d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5197d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5197d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5197d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5197d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5197d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQueries**</span><span class="sxs-lookup"><span data-stu-id="5197d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5197d-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5197d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5197d-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5197d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5197d-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5197d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5197d-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="5197d-114">Attributes</span></span>  
 <span data-ttu-id="5197d-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5197d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5197d-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5197d-116">Child Elements</span></span>  
  
|<span data-ttu-id="5197d-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5197d-117">Element</span></span>|<span data-ttu-id="5197d-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5197d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5197d-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="5197d-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="5197d-120">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="5197d-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5197d-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5197d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5197d-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="5197d-122">Element</span></span>|<span data-ttu-id="5197d-123">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5197d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5197d-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5197d-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="5197d-125">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="5197d-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5197d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="5197d-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5197d-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5197d-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5197d-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5197d-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
