---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 763754b95a7f39c7f35e05df28589b69352168e6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152429"
---
# \<activityScheduledQueries>
<span data-ttu-id="27593-101">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="27593-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="27593-102">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="27593-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="27593-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="27593-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="27593-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27593-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27593-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="27593-105">Attributes and Elements</span></span>  
 <span data-ttu-id="27593-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="27593-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27593-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="27593-107">Attributes</span></span>  
 <span data-ttu-id="27593-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="27593-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="27593-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="27593-109">Child Elements</span></span>  
  
|<span data-ttu-id="27593-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="27593-110">Element</span></span>|<span data-ttu-id="27593-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="27593-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="27593-112">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="27593-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27593-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="27593-113">Parent Elements</span></span>  
  
|<span data-ttu-id="27593-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="27593-114">Element</span></span>|<span data-ttu-id="27593-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="27593-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="27593-116">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="27593-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27593-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="27593-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="27593-118">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="27593-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="27593-119">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="27593-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
