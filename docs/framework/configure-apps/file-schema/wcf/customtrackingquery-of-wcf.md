---
title: <customTrackingQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855424"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="50cc4-102">\<customTrackingQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="50cc4-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="50cc4-103">Representa una consulta que se usa para realizar el seguimiento de los eventos que se definen en las actividades de código.</span><span class="sxs-lookup"><span data-stu-id="50cc4-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="50cc4-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="50cc4-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="50cc4-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="50cc4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="50cc4-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="50cc4-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="50cc4-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="50cc4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="50cc4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="50cc4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="50cc4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="50cc4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> customTrackingQueries**](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="50cc4-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="50cc4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> customTrackingQuery**</span><span class="sxs-lookup"><span data-stu-id="50cc4-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50cc4-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50cc4-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50cc4-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50cc4-115">Attributes and elements</span></span>  

<span data-ttu-id="50cc4-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50cc4-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50cc4-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="50cc4-117">Attributes</span></span>  
  
|<span data-ttu-id="50cc4-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="50cc4-118">Attribute</span></span>|<span data-ttu-id="50cc4-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="50cc4-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="50cc4-120">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="50cc4-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="50cc4-121">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="50cc4-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50cc4-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50cc4-122">Child elements</span></span>

<span data-ttu-id="50cc4-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="50cc4-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="50cc4-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50cc4-124">Parent elements</span></span>

|<span data-ttu-id="50cc4-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="50cc4-125">Element</span></span>|<span data-ttu-id="50cc4-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="50cc4-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50cc4-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="50cc4-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="50cc4-128">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="50cc4-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="50cc4-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="50cc4-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="50cc4-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="50cc4-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="50cc4-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="50cc4-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
