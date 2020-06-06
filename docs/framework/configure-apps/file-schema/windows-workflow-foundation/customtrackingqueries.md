---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152266"
---
# \<customTrackingQueries>
<span data-ttu-id="6a210-101">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="6a210-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="6a210-102">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="6a210-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="6a210-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="6a210-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="6a210-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a210-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a210-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6a210-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6a210-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6a210-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a210-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6a210-107">Attributes</span></span>  
 <span data-ttu-id="6a210-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6a210-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6a210-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6a210-109">Child Elements</span></span>  
  
|<span data-ttu-id="6a210-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a210-110">Element</span></span>|<span data-ttu-id="6a210-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a210-111">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="6a210-112">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="6a210-112">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a210-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6a210-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6a210-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6a210-114">Element</span></span>|<span data-ttu-id="6a210-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a210-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="6a210-116">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="6a210-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a210-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6a210-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6a210-118">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6a210-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6a210-119">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6a210-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
