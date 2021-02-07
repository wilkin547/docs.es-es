---
description: 'Más información sobre: <customTrackingQueries> de WCF'
title: <customTrackingQueries> de WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: ac1cdcc074201b97344b3727f6957e1b62c88dab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754477"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="df6fd-103">\<customTrackingQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="df6fd-103">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="df6fd-104">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="df6fd-104">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="df6fd-105">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="df6fd-105">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="df6fd-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="df6fd-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="df6fd-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df6fd-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df6fd-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="df6fd-108">Attributes and elements</span></span>

<span data-ttu-id="df6fd-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="df6fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df6fd-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="df6fd-110">Attributes</span></span>

<span data-ttu-id="df6fd-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="df6fd-111">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="df6fd-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="df6fd-112">Child elements</span></span>
  
|<span data-ttu-id="df6fd-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="df6fd-113">Element</span></span>|<span data-ttu-id="df6fd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="df6fd-114">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="df6fd-115">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="df6fd-115">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="df6fd-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="df6fd-116">Parent elements</span></span>  
  
|<span data-ttu-id="df6fd-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="df6fd-117">Element</span></span>|<span data-ttu-id="df6fd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="df6fd-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="df6fd-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="df6fd-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="df6fd-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="df6fd-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="df6fd-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="df6fd-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="df6fd-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="df6fd-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
