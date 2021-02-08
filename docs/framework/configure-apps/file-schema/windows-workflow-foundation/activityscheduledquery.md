---
description: 'Más información acerca de: <activityScheduledQuery>'
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 72aa9c2d3480488d4468d008fa8a4306929c190d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802117"
---
# \<activityScheduledQuery>

<span data-ttu-id="e44cd-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="e44cd-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e44cd-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e44cd-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="e44cd-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e44cd-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="e44cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e44cd-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e44cd-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e44cd-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e44cd-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e44cd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e44cd-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e44cd-108">Attributes</span></span>  
  
|<span data-ttu-id="e44cd-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="e44cd-109">Attribute</span></span>|<span data-ttu-id="e44cd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="e44cd-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e44cd-111">activityName</span><span class="sxs-lookup"><span data-stu-id="e44cd-111">activityName</span></span>|<span data-ttu-id="e44cd-112">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="e44cd-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="e44cd-113">childActivityName</span><span class="sxs-lookup"><span data-stu-id="e44cd-113">childActivityName</span></span>|<span data-ttu-id="e44cd-114">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="e44cd-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e44cd-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e44cd-115">Child Elements</span></span>  

 <span data-ttu-id="e44cd-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e44cd-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e44cd-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e44cd-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e44cd-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e44cd-118">Element</span></span>|<span data-ttu-id="e44cd-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e44cd-119">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="e44cd-120">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="e44cd-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e44cd-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e44cd-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e44cd-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e44cd-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e44cd-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e44cd-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
