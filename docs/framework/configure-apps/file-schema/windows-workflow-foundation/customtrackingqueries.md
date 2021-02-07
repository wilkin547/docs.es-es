---
description: 'Más información acerca de: <customTrackingQueries>'
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 3601950742eb002f43969bea4612e830d8365509
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719064"
---
# \<customTrackingQueries>

<span data-ttu-id="f038c-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="f038c-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f038c-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="f038c-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f038c-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="f038c-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="f038c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f038c-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f038c-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f038c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f038c-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f038c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f038c-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="f038c-108">Attributes</span></span>  

 <span data-ttu-id="f038c-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f038c-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f038c-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f038c-110">Child Elements</span></span>  
  
|<span data-ttu-id="f038c-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="f038c-111">Element</span></span>|<span data-ttu-id="f038c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="f038c-112">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="f038c-113">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="f038c-113">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f038c-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f038c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="f038c-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="f038c-115">Element</span></span>|<span data-ttu-id="f038c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f038c-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="f038c-117">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="f038c-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f038c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f038c-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f038c-119">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f038c-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f038c-120">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f038c-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
