---
description: 'Más información sobre: <customTrackingQuery> de WCF'
title: <customTrackingQuery> de WCF
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 3eac26ee94a95b480d743e3c6ec554a84b8747a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754464"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="0188d-103">\<customTrackingQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="0188d-103">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="0188d-104">Representa una consulta que se usa para realizar el seguimiento de los eventos que se definen en las actividades de código.</span><span class="sxs-lookup"><span data-stu-id="0188d-104">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="0188d-105">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="0188d-105">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="0188d-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="0188d-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="0188d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0188d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0188d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0188d-108">Attributes and elements</span></span>  

<span data-ttu-id="0188d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0188d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0188d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="0188d-110">Attributes</span></span>  
  
|<span data-ttu-id="0188d-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="0188d-111">Attribute</span></span>|<span data-ttu-id="0188d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0188d-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="0188d-113">Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0188d-113">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="0188d-114">Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.</span><span class="sxs-lookup"><span data-stu-id="0188d-114">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0188d-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0188d-115">Child elements</span></span>

<span data-ttu-id="0188d-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0188d-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="0188d-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0188d-117">Parent elements</span></span>

|<span data-ttu-id="0188d-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="0188d-118">Element</span></span>|<span data-ttu-id="0188d-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="0188d-119">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="0188d-120">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="0188d-120">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="0188d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0188d-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="0188d-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="0188d-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="0188d-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0188d-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
