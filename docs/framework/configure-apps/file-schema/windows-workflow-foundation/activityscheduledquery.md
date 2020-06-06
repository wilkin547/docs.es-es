---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152416"
---
# \<activityScheduledQuery>
<span data-ttu-id="4edcc-101">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="4edcc-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4edcc-102">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="4edcc-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="4edcc-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="4edcc-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="4edcc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4edcc-104">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String"
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4edcc-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4edcc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4edcc-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4edcc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4edcc-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4edcc-107">Attributes</span></span>  
  
|<span data-ttu-id="4edcc-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4edcc-108">Attribute</span></span>|<span data-ttu-id="4edcc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4edcc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4edcc-110">activityName</span><span class="sxs-lookup"><span data-stu-id="4edcc-110">activityName</span></span>|<span data-ttu-id="4edcc-111">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="4edcc-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="4edcc-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="4edcc-112">childActivityName</span></span>|<span data-ttu-id="4edcc-113">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="4edcc-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4edcc-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4edcc-114">Child Elements</span></span>  
 <span data-ttu-id="4edcc-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4edcc-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4edcc-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4edcc-116">Parent Elements</span></span>  
  
|<span data-ttu-id="4edcc-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="4edcc-117">Element</span></span>|<span data-ttu-id="4edcc-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4edcc-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="4edcc-119">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="4edcc-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4edcc-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4edcc-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="4edcc-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4edcc-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4edcc-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4edcc-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
