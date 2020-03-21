---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 89297b3a7d64f4300a735d8512230d441836c634
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152312"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="20682-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="20682-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="20682-102">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="20682-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="20682-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="20682-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="20682-104">Para obtener más información sobre el seguimiento de consultas de perfiles, consulte Seguimiento de [perfiles](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="20682-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="20682-105">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="20682-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="20682-106">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="20682-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="20682-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="20682-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="20682-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="20682-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="20682-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="20682-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="20682-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span><span class="sxs-lookup"><span data-stu-id="20682-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20682-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="20682-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20682-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="20682-112">Attributes and Elements</span></span>  
 <span data-ttu-id="20682-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="20682-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20682-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="20682-114">Attributes</span></span>  
 <span data-ttu-id="20682-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="20682-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20682-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="20682-116">Child Elements</span></span>  
  
|<span data-ttu-id="20682-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="20682-117">Element</span></span>|<span data-ttu-id="20682-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="20682-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20682-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="20682-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="20682-120">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="20682-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20682-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="20682-121">Parent Elements</span></span>  
  
|<span data-ttu-id="20682-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="20682-122">Element</span></span>|<span data-ttu-id="20682-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="20682-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="20682-124">\<flujo de trabajo></span><span class="sxs-lookup"><span data-stu-id="20682-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="20682-125">Elemento de configuración que contiene todas las consultas de un flujo de trabajo específico identificado por la propiedad **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="20682-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20682-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="20682-126">See also</span></span>

- [<span data-ttu-id="20682-127">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="20682-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="20682-128">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="20682-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
