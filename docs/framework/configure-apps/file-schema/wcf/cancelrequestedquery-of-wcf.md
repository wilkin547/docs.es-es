---
title: <cancelRequestedQuery>de WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850053"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="3bfe8-102">\<cancelRequestedQuery > de WCF</span><span class="sxs-lookup"><span data-stu-id="3bfe8-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="3bfe8-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3bfe8-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="3bfe8-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3bfe8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="3bfe8-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3bfe8-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3bfe8-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="3bfe8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="3bfe8-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="3bfe8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="3bfe8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="3bfe8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cancelRequestedQueries**](cancelrequestedqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="3bfe8-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)</span></span>\
<span data-ttu-id="3bfe8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> cancelRequestedQuery**</span><span class="sxs-lookup"><span data-stu-id="3bfe8-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="3bfe8-114">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bfe8-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bfe8-115">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3bfe8-115">Attributes and elements</span></span>

<span data-ttu-id="3bfe8-116">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="3bfe8-117">Atributos</span><span class="sxs-lookup"><span data-stu-id="3bfe8-117">Attributes</span></span>  
  
|<span data-ttu-id="3bfe8-118">Atributo</span><span class="sxs-lookup"><span data-stu-id="3bfe8-118">Attribute</span></span>|<span data-ttu-id="3bfe8-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bfe8-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="3bfe8-120">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="3bfe8-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bfe8-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3bfe8-122">Child elements</span></span>

<span data-ttu-id="3bfe8-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="3bfe8-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3bfe8-124">Parent elements</span></span>
  
|<span data-ttu-id="3bfe8-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3bfe8-125">Element</span></span>|<span data-ttu-id="3bfe8-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3bfe8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bfe8-127">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="3bfe8-127">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="3bfe8-128">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3bfe8-128">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3bfe8-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bfe8-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3bfe8-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3bfe8-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3bfe8-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3bfe8-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
