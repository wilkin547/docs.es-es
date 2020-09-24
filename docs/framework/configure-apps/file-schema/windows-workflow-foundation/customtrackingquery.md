---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 59a76ea772dc8d06c390e3bca9d531df5f11e5f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148729"
---
# \<customTrackingQuery>

<span data-ttu-id="1c837-101">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="1c837-101">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1c837-102">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="1c837-102">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1c837-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="1c837-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="1c837-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c837-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c837-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1c837-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1c837-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1c837-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c837-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="1c837-107">Attributes</span></span>  
  
|<span data-ttu-id="1c837-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="1c837-108">Attribute</span></span>|<span data-ttu-id="1c837-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c837-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1c837-110">activityName</span><span class="sxs-lookup"><span data-stu-id="1c837-110">activityName</span></span>|<span data-ttu-id="1c837-111">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1c837-111">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="1c837-112">name</span><span class="sxs-lookup"><span data-stu-id="1c837-112">name</span></span>|<span data-ttu-id="1c837-113">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="1c837-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1c837-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1c837-114">Child Elements</span></span>  

 <span data-ttu-id="1c837-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1c837-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1c837-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1c837-116">Parent Elements</span></span>  
  
|<span data-ttu-id="1c837-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="1c837-117">Element</span></span>|<span data-ttu-id="1c837-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c837-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="1c837-119">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="1c837-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c837-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c837-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1c837-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1c837-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1c837-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="1c837-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
