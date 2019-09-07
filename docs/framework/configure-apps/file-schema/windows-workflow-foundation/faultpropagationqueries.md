---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398728"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="dabd1-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="dabd1-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="dabd1-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dabd1-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dabd1-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="dabd1-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="dabd1-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dabd1-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="dabd1-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="dabd1-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="dabd1-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="dabd1-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="dabd1-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dabd1-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dabd1-108">&nbsp;&nbsp;[ **\<integrado. > De ServiceModel**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dabd1-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="dabd1-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="dabd1-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="dabd1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="dabd1-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="dabd1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="dabd1-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="dabd1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQueries**</span><span class="sxs-lookup"><span data-stu-id="dabd1-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="dabd1-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dabd1-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dabd1-114">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dabd1-114">Attributes and Elements</span></span>  
 <span data-ttu-id="dabd1-115">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dabd1-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dabd1-116">Atributos</span><span class="sxs-lookup"><span data-stu-id="dabd1-116">Attributes</span></span>  
 <span data-ttu-id="dabd1-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dabd1-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dabd1-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dabd1-118">Child Elements</span></span>  
  
|<span data-ttu-id="dabd1-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dabd1-119">Element</span></span>|<span data-ttu-id="dabd1-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dabd1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dabd1-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="dabd1-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="dabd1-122">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="dabd1-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="dabd1-123">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="dabd1-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dabd1-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dabd1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dabd1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="dabd1-125">Element</span></span>|<span data-ttu-id="dabd1-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="dabd1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dabd1-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="dabd1-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="dabd1-128">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="dabd1-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dabd1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="dabd1-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="dabd1-130">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="dabd1-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="dabd1-131">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dabd1-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
