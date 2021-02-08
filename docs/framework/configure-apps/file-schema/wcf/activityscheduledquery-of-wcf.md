---
description: 'Más información sobre: <activityScheduledQuery> de WCF'
title: <activityScheduledQuery> de WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b1b5f971dccfbc650ee12a08a9ae2fa7b745db50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802364"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="b0f68-103">\<activityScheduledQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="b0f68-103">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="b0f68-104">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b0f68-104">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b0f68-105">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b0f68-105">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b0f68-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b0f68-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="b0f68-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0f68-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0f68-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0f68-108">Attributes and elements</span></span>  

<span data-ttu-id="b0f68-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0f68-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0f68-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0f68-110">Attributes</span></span>  
  
|<span data-ttu-id="b0f68-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0f68-111">Attribute</span></span>|<span data-ttu-id="b0f68-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f68-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b0f68-113">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b0f68-113">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b0f68-114">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b0f68-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0f68-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0f68-115">Child elements</span></span>

<span data-ttu-id="b0f68-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0f68-116">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b0f68-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0f68-117">Parent elements</span></span>  
  
|<span data-ttu-id="b0f68-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0f68-118">Element</span></span>|<span data-ttu-id="b0f68-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f68-119">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="b0f68-120">Colección de consultas que se usan para realizar el seguimiento de una actividad programada para su ejecución mediante una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b0f68-120">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0f68-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0f68-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b0f68-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b0f68-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b0f68-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b0f68-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
