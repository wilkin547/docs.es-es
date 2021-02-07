---
description: 'Más información sobre: <faultPropagationQueries> de WCF'
title: <faultPropagationQueries> de WCF
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: e3ed504b3aada87246fabe54c0b32ef5ad60b34b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684443"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="33b30-103">\<faultPropagationQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="33b30-103">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="33b30-104">Representa una colección de consultas que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b30-104">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="33b30-105">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="33b30-105">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="33b30-106">Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b30-106">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="33b30-107">La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.</span><span class="sxs-lookup"><span data-stu-id="33b30-107">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="33b30-108">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="33b30-108">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="33b30-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33b30-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33b30-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="33b30-110">Attributes and elements</span></span>

<span data-ttu-id="33b30-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="33b30-111">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="33b30-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="33b30-112">Attributes</span></span>

<span data-ttu-id="33b30-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="33b30-113">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="33b30-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="33b30-114">Child elements</span></span>

|<span data-ttu-id="33b30-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b30-115">Element</span></span>|<span data-ttu-id="33b30-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="33b30-116">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="33b30-117">Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.</span><span class="sxs-lookup"><span data-stu-id="33b30-117">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="33b30-118">Este evento se produce cada vez que un FaultHandler procesa un error.</span><span class="sxs-lookup"><span data-stu-id="33b30-118">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="33b30-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="33b30-119">Parent elements</span></span>  
  
|<span data-ttu-id="33b30-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="33b30-120">Element</span></span>|<span data-ttu-id="33b30-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="33b30-121">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="33b30-122">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="33b30-122">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33b30-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="33b30-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="33b30-124">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="33b30-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="33b30-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="33b30-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
