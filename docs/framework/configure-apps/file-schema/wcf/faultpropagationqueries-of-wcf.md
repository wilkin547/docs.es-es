---
title: <faultPropagationQueries>de WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855267"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="4bdf5-102">\<faultPropagationQueries > de WCF</span><span class="sxs-lookup"><span data-stu-id="4bdf5-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="4bdf5-103">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4bdf5-104">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="4bdf5-105">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="4bdf5-106">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="4bdf5-107">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4bdf5-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4bdf5-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4bdf5-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4bdf5-109">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4bdf5-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4bdf5-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de seguimiento**](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4bdf5-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="4bdf5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<perfiles >** </span><span class="sxs-lookup"><span data-stu-id="4bdf5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="4bdf5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> trackingProfile**](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4bdf5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="4bdf5-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> de flujo de trabajo**](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="4bdf5-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="4bdf5-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> faultPropagationQueries**</span><span class="sxs-lookup"><span data-stu-id="4bdf5-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bdf5-115">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bdf5-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bdf5-116">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4bdf5-116">Attributes and elements</span></span>

<span data-ttu-id="4bdf5-117">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="4bdf5-118">Atributos</span><span class="sxs-lookup"><span data-stu-id="4bdf5-118">Attributes</span></span>

<span data-ttu-id="4bdf5-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="4bdf5-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4bdf5-120">Child elements</span></span>

|<span data-ttu-id="4bdf5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bdf5-121">Element</span></span>|<span data-ttu-id="4bdf5-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4bdf5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bdf5-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="4bdf5-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="4bdf5-124">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="4bdf5-125">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bdf5-126">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4bdf5-126">Parent elements</span></span>  
  
|<span data-ttu-id="4bdf5-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bdf5-127">Element</span></span>|<span data-ttu-id="4bdf5-128">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4bdf5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bdf5-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4bdf5-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="4bdf5-130">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="4bdf5-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4bdf5-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bdf5-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4bdf5-132">Seguimiento y traza de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="4bdf5-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4bdf5-133">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4bdf5-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
