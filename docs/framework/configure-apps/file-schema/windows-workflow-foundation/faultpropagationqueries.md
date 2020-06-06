---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152136"
---
# \<faultPropagationQueries>
<span data-ttu-id="15591-101">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="15591-101">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="15591-102">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="15591-102">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="15591-103">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="15591-103">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="15591-104">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="15591-104">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="15591-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="15591-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="15591-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15591-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15591-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="15591-107">Attributes and Elements</span></span>  
 <span data-ttu-id="15591-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="15591-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15591-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="15591-109">Attributes</span></span>  
 <span data-ttu-id="15591-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="15591-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15591-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="15591-111">Child Elements</span></span>  
  
|<span data-ttu-id="15591-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="15591-112">Element</span></span>|<span data-ttu-id="15591-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="15591-113">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="15591-114">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="15591-114">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="15591-115">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="15591-115">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15591-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="15591-116">Parent Elements</span></span>  
  
|<span data-ttu-id="15591-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="15591-117">Element</span></span>|<span data-ttu-id="15591-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="15591-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="15591-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="15591-119">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15591-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="15591-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="15591-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="15591-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="15591-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="15591-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
