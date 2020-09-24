---
title: <activityScheduledQueries> de WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 86f196437b2230d6541570aa8994d99e7b340f66
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151199"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="03120-102">\<activityScheduledQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="03120-102">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="03120-103">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="03120-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="03120-104">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="03120-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="03120-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="03120-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="03120-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03120-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03120-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="03120-107">Attributes and elements</span></span>  

<span data-ttu-id="03120-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="03120-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03120-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="03120-109">Attributes</span></span>  

<span data-ttu-id="03120-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="03120-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="03120-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="03120-111">Child elements</span></span>  
  
|<span data-ttu-id="03120-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="03120-112">Element</span></span>|<span data-ttu-id="03120-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="03120-113">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="03120-114">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="03120-114">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03120-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="03120-115">Parent elements</span></span>  
  
|<span data-ttu-id="03120-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="03120-116">Element</span></span>|<span data-ttu-id="03120-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="03120-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="03120-118">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="03120-118">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03120-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="03120-119">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="03120-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="03120-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="03120-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="03120-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
