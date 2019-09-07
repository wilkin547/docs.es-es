---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5de459717fdc0dbf946f12dceda18dce79ca4b06
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398815"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="3a792-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="3a792-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="3a792-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3a792-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3a792-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3a792-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3a792-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="3a792-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3a792-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a792-106">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="3a792-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="3a792-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="3a792-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="3a792-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> cancelRequestedQueries**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="3a792-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="3a792-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> cancelRequestedQuery**</span><span class="sxs-lookup"><span data-stu-id="3a792-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a792-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a792-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a792-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a792-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3a792-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a792-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a792-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a792-115">Attributes</span></span>  
  
|<span data-ttu-id="3a792-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3a792-116">Attribute</span></span>|<span data-ttu-id="3a792-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3a792-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a792-118">activityName</span><span class="sxs-lookup"><span data-stu-id="3a792-118">activityName</span></span>|<span data-ttu-id="3a792-119">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3a792-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3a792-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3a792-120">childActivityName</span></span>|<span data-ttu-id="3a792-121">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="3a792-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a792-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a792-122">Child Elements</span></span>  
 <span data-ttu-id="3a792-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a792-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a792-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a792-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3a792-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a792-125">Element</span></span>|<span data-ttu-id="3a792-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3a792-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a792-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="3a792-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="3a792-128">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3a792-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3a792-129">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="3a792-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a792-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a792-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a792-131">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="3a792-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a792-132">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3a792-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
