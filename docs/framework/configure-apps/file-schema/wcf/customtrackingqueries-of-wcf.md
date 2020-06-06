---
title: <customTrackingQueries>de WCF
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855440"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="06fc1-102">\<customTrackingQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="06fc1-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="06fc1-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="06fc1-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="06fc1-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.</span><span class="sxs-lookup"><span data-stu-id="06fc1-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="06fc1-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="06fc1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**  

## <a name="syntax"></a><span data-ttu-id="06fc1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06fc1-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06fc1-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="06fc1-107">Attributes and elements</span></span>

<span data-ttu-id="06fc1-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="06fc1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="06fc1-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="06fc1-109">Attributes</span></span>

<span data-ttu-id="06fc1-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="06fc1-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="06fc1-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="06fc1-111">Child elements</span></span>
  
|<span data-ttu-id="06fc1-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="06fc1-112">Element</span></span>|<span data-ttu-id="06fc1-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="06fc1-113">Description</span></span>|  
|-------------|-----------------|  
|[\<customTrackingQuery>](customtrackingquery-of-wcf.md)|<span data-ttu-id="06fc1-114">Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.</span><span class="sxs-lookup"><span data-stu-id="06fc1-114">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="06fc1-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="06fc1-115">Parent elements</span></span>  
  
|<span data-ttu-id="06fc1-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="06fc1-116">Element</span></span>|<span data-ttu-id="06fc1-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="06fc1-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="06fc1-118">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="06fc1-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="06fc1-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="06fc1-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="06fc1-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="06fc1-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="06fc1-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="06fc1-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
