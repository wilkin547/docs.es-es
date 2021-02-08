---
description: 'Más información acerca de: <customTrackingQuery>'
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 24857aca39aad825a3dd4eca83fa3a51ec440b25
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795097"
---
# \<customTrackingQuery>

<span data-ttu-id="edd9f-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="edd9f-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="edd9f-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="edd9f-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="edd9f-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="edd9f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="edd9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edd9f-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="edd9f-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="edd9f-106">Attributes and Elements</span></span>  

 <span data-ttu-id="edd9f-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="edd9f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="edd9f-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="edd9f-108">Attributes</span></span>  
  
|<span data-ttu-id="edd9f-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="edd9f-109">Attribute</span></span>|<span data-ttu-id="edd9f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="edd9f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="edd9f-111">activityName</span><span class="sxs-lookup"><span data-stu-id="edd9f-111">activityName</span></span>|<span data-ttu-id="edd9f-112">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="edd9f-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="edd9f-113">name</span><span class="sxs-lookup"><span data-stu-id="edd9f-113">name</span></span>|<span data-ttu-id="edd9f-114">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="edd9f-114">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="edd9f-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="edd9f-115">Child Elements</span></span>  

 <span data-ttu-id="edd9f-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="edd9f-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="edd9f-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="edd9f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="edd9f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="edd9f-118">Element</span></span>|<span data-ttu-id="edd9f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="edd9f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery.md)|<span data-ttu-id="edd9f-120">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="edd9f-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="edd9f-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="edd9f-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="edd9f-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="edd9f-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="edd9f-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="edd9f-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
