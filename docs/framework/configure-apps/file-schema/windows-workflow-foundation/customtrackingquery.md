---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152214"
---
# <a name="customtrackingquery"></a><span data-ttu-id="c5ca2-101">\<> customTrackingQuery</span><span class="sxs-lookup"><span data-stu-id="c5ca2-101">\<customTrackingQuery></span></span>
<span data-ttu-id="c5ca2-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="c5ca2-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="c5ca2-104">Para obtener más información sobre el seguimiento de consultas de perfiles, consulte Seguimiento de [perfiles](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c5ca2-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c5ca2-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c5ca2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="c5ca2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="c5ca2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="c5ca2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>customTrackingQueries**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="c5ca2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="c5ca2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>customTrackingQuery**</span><span class="sxs-lookup"><span data-stu-id="c5ca2-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5ca2-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5ca2-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5ca2-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c5ca2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c5ca2-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5ca2-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="c5ca2-115">Attributes</span></span>  
  
|<span data-ttu-id="c5ca2-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="c5ca2-116">Attribute</span></span>|<span data-ttu-id="c5ca2-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5ca2-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5ca2-118">activityName</span><span class="sxs-lookup"><span data-stu-id="c5ca2-118">activityName</span></span>|<span data-ttu-id="c5ca2-119">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="c5ca2-120">name</span><span class="sxs-lookup"><span data-stu-id="c5ca2-120">name</span></span>|<span data-ttu-id="c5ca2-121">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5ca2-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c5ca2-122">Child Elements</span></span>  
 <span data-ttu-id="c5ca2-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5ca2-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c5ca2-124">Parent Elements</span></span>  
  
|<span data-ttu-id="c5ca2-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="c5ca2-125">Element</span></span>|<span data-ttu-id="c5ca2-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5ca2-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5ca2-127">\<>customTrackingQuery</span><span class="sxs-lookup"><span data-stu-id="c5ca2-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="c5ca2-128">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="c5ca2-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5ca2-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5ca2-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c5ca2-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c5ca2-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c5ca2-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c5ca2-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
