---
title: <activityScheduledQuery>de WCF
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850464"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="b4bee-102">\<activityScheduledQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="b4bee-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="b4bee-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b4bee-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="b4bee-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="b4bee-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="b4bee-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="b4bee-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="b4bee-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4bee-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b4bee-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b4bee-107">Attributes and elements</span></span>  

<span data-ttu-id="b4bee-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b4bee-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b4bee-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="b4bee-109">Attributes</span></span>  
  
|<span data-ttu-id="b4bee-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="b4bee-110">Attribute</span></span>|<span data-ttu-id="b4bee-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4bee-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="b4bee-112">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b4bee-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="b4bee-113">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b4bee-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b4bee-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b4bee-114">Child elements</span></span>

<span data-ttu-id="b4bee-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b4bee-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="b4bee-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b4bee-116">Parent elements</span></span>  
  
|<span data-ttu-id="b4bee-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b4bee-117">Element</span></span>|<span data-ttu-id="b4bee-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4bee-118">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQueries>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="b4bee-119">Colección de consultas que se usan para realizar el seguimiento de una actividad programada para su ejecución mediante una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="b4bee-119">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b4bee-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4bee-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="b4bee-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b4bee-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b4bee-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b4bee-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
