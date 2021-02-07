---
description: 'Más información acerca de: <faultPropagationQueries>'
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 13bd19a3673846bfbd641cd2f8eeafc20b8186f8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719075"
---
# \<faultPropagationQueries>

<span data-ttu-id="65b2e-102">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="65b2e-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="65b2e-103">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="65b2e-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="65b2e-104">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="65b2e-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="65b2e-105">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="65b2e-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="65b2e-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="65b2e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**
  
## <a name="syntax"></a><span data-ttu-id="65b2e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65b2e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65b2e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="65b2e-108">Attributes and Elements</span></span>  

 <span data-ttu-id="65b2e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="65b2e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65b2e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="65b2e-110">Attributes</span></span>  

 <span data-ttu-id="65b2e-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="65b2e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="65b2e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="65b2e-112">Child Elements</span></span>  
  
|<span data-ttu-id="65b2e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="65b2e-113">Element</span></span>|<span data-ttu-id="65b2e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="65b2e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="65b2e-115">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="65b2e-115">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="65b2e-116">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="65b2e-116">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="65b2e-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="65b2e-117">Parent Elements</span></span>  
  
|<span data-ttu-id="65b2e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="65b2e-118">Element</span></span>|<span data-ttu-id="65b2e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="65b2e-119">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="65b2e-120">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="65b2e-120">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="65b2e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="65b2e-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="65b2e-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="65b2e-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="65b2e-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="65b2e-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
