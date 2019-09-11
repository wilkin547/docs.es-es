---
title: <cancelRequestedQueries>de WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850098"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="c0a57-102">\<cancelRequestedQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="c0a57-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="c0a57-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="c0a57-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c0a57-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="c0a57-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="c0a57-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="c0a57-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c0a57-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c0a57-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c0a57-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c0a57-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c0a57-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c0a57-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="c0a57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="c0a57-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="c0a57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c0a57-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="c0a57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="c0a57-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="c0a57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> cancelRequestedQueries**</span><span class="sxs-lookup"><span data-stu-id="c0a57-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0a57-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0a57-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c0a57-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c0a57-114">Attributes and elements</span></span>  

<span data-ttu-id="c0a57-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c0a57-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c0a57-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="c0a57-116">Attributes</span></span>

<span data-ttu-id="c0a57-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c0a57-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="c0a57-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c0a57-118">Child elements</span></span>
  
|<span data-ttu-id="c0a57-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0a57-119">Element</span></span>|<span data-ttu-id="c0a57-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c0a57-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0a57-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c0a57-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="c0a57-122">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="c0a57-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c0a57-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c0a57-123">Parent elements</span></span>  
  
|<span data-ttu-id="c0a57-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="c0a57-124">Element</span></span>|<span data-ttu-id="c0a57-125">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c0a57-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c0a57-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c0a57-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="c0a57-127">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="c0a57-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c0a57-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0a57-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="c0a57-129">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="c0a57-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c0a57-130">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c0a57-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
