---
description: 'Más información acerca de: <activityScheduledQueries>'
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 1f43642edffea782a9e5257a3568868645994a46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729841"
---
# \<activityScheduledQueries>

<span data-ttu-id="e02e8-102">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="e02e8-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e02e8-103">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e02e8-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="e02e8-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="e02e8-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="e02e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e02e8-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e02e8-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e02e8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="e02e8-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e02e8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e02e8-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="e02e8-108">Attributes</span></span>  

 <span data-ttu-id="e02e8-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e02e8-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e02e8-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e02e8-110">Child Elements</span></span>  
  
|<span data-ttu-id="e02e8-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="e02e8-111">Element</span></span>|<span data-ttu-id="e02e8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e02e8-112">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery.md)|<span data-ttu-id="e02e8-113">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="e02e8-113">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e02e8-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e02e8-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e02e8-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="e02e8-115">Element</span></span>|<span data-ttu-id="e02e8-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="e02e8-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="e02e8-117">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="e02e8-117">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e02e8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e02e8-118">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e02e8-119">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e02e8-119">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e02e8-120">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e02e8-120">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
