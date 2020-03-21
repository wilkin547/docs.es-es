---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152136"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="43783-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="43783-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="43783-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="43783-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="43783-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="43783-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="43783-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="43783-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="43783-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="43783-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="43783-106">Para obtener más información sobre el seguimiento de consultas de perfil, consulte [Perfiles](../../../windows-workflow-foundation/tracking-profiles.md)de seguimiento .</span><span class="sxs-lookup"><span data-stu-id="43783-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="43783-107">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="43783-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="43783-108">&nbsp;&nbsp;[**\<Sistema.>De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="43783-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="43783-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<seguimiento>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="43783-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="43783-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="43783-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="43783-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<flujo de trabajo>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="43783-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="43783-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span><span class="sxs-lookup"><span data-stu-id="43783-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="43783-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43783-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43783-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="43783-114">Attributes and Elements</span></span>  
 <span data-ttu-id="43783-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="43783-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43783-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="43783-116">Attributes</span></span>  
 <span data-ttu-id="43783-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="43783-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43783-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="43783-118">Child Elements</span></span>  
  
|<span data-ttu-id="43783-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="43783-119">Element</span></span>|<span data-ttu-id="43783-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="43783-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43783-121">\<>faultPropagationQuery</span><span class="sxs-lookup"><span data-stu-id="43783-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="43783-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="43783-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="43783-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="43783-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43783-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="43783-124">Parent Elements</span></span>  
  
|<span data-ttu-id="43783-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="43783-125">Element</span></span>|<span data-ttu-id="43783-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="43783-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43783-127">\<flujo de trabajo></span><span class="sxs-lookup"><span data-stu-id="43783-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="43783-128">Elemento de configuración que contiene todas las consultas de un flujo de trabajo específico identificado por la propiedad **activityDefinitionId.**</span><span class="sxs-lookup"><span data-stu-id="43783-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43783-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="43783-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="43783-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="43783-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="43783-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="43783-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
