---
title: <customTrackingQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855424"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="9885a-102">\<customTrackingQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="9885a-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="9885a-103">Representa una consulta que se usa para realizar el seguimiento de los eventos que se definen en las actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9885a-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="9885a-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="9885a-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="9885a-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="9885a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="9885a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9885a-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9885a-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9885a-107">Attributes and elements</span></span>  

<span data-ttu-id="9885a-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9885a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9885a-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="9885a-109">Attributes</span></span>  
  
|<span data-ttu-id="9885a-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="9885a-110">Attribute</span></span>|<span data-ttu-id="9885a-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9885a-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="9885a-112">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9885a-112">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="9885a-113">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="9885a-113">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9885a-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9885a-114">Child elements</span></span>

<span data-ttu-id="9885a-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9885a-115">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9885a-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9885a-116">Parent elements</span></span>

|<span data-ttu-id="9885a-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="9885a-117">Element</span></span>|<span data-ttu-id="9885a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9885a-118">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="9885a-119">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="9885a-119">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="9885a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9885a-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9885a-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9885a-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9885a-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9885a-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
