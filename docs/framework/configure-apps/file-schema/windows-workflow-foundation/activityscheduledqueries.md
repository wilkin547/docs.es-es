---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 936267f7d61dfd09af45ddb96b4406c92c30b3b2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148781"
---
# \<activityScheduledQueries>

<span data-ttu-id="3a842-101">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3a842-101">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="3a842-102">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="3a842-102">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="3a842-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="3a842-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="3a842-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a842-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a842-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3a842-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3a842-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3a842-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a842-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3a842-107">Attributes</span></span>  

 <span data-ttu-id="3a842-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3a842-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a842-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3a842-109">Child Elements</span></span>  
  
|<span data-ttu-id="3a842-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a842-110">Element</span></span>|<span data-ttu-id="3a842-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a842-111">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="3a842-112">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="3a842-112">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a842-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3a842-113">Parent Elements</span></span>  
  
|<span data-ttu-id="3a842-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="3a842-114">Element</span></span>|<span data-ttu-id="3a842-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a842-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="3a842-116">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="3a842-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a842-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a842-117">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3a842-118">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3a842-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3a842-119">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3a842-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
