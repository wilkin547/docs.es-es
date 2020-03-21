---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152292"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="5852c-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="5852c-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="5852c-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="5852c-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5852c-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5852c-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="5852c-104">Para obtener más información sobre el seguimiento de consultas de perfil, consulte [Perfiles](../../../windows-workflow-foundation/tracking-profiles.md)de seguimiento .</span><span class="sxs-lookup"><span data-stu-id="5852c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5852c-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5852c-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5852c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5852c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5852c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5852c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="5852c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="5852c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span><span class="sxs-lookup"><span data-stu-id="5852c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5852c-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5852c-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5852c-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5852c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5852c-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5852c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5852c-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="5852c-115">Attributes</span></span>  
  
|<span data-ttu-id="5852c-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="5852c-116">Attribute</span></span>|<span data-ttu-id="5852c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="5852c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5852c-118">activityName</span><span class="sxs-lookup"><span data-stu-id="5852c-118">activityName</span></span>|<span data-ttu-id="5852c-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="5852c-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="5852c-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="5852c-120">childActivityName</span></span>|<span data-ttu-id="5852c-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="5852c-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5852c-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5852c-122">Child Elements</span></span>  
 <span data-ttu-id="5852c-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5852c-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5852c-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5852c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5852c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5852c-125">Element</span></span>|<span data-ttu-id="5852c-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5852c-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5852c-127">\<>faultPropagationQuery</span><span class="sxs-lookup"><span data-stu-id="5852c-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="5852c-128">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="5852c-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5852c-129">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="5852c-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5852c-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5852c-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5852c-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="5852c-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5852c-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5852c-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
