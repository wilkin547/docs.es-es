---
description: 'Más información sobre: <activityScheduledQueries> de WCF'
title: <activityScheduledQueries> de WCF
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: b92bb2827b4c8bce43e4ee0b8dc03c7be124e3da
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782252"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="fbd88-103">\<activityScheduledQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="fbd88-103">\<activityScheduledQueries> of WCF</span></span>

<span data-ttu-id="fbd88-104">Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="fbd88-104">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="fbd88-105">La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.</span><span class="sxs-lookup"><span data-stu-id="fbd88-105">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="fbd88-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="fbd88-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="fbd88-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbd88-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fbd88-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fbd88-108">Attributes and elements</span></span>  

<span data-ttu-id="fbd88-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fbd88-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fbd88-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="fbd88-110">Attributes</span></span>  

<span data-ttu-id="fbd88-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fbd88-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fbd88-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fbd88-112">Child elements</span></span>  
  
|<span data-ttu-id="fbd88-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbd88-113">Element</span></span>|<span data-ttu-id="fbd88-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbd88-114">Description</span></span>|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="fbd88-115">Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="fbd88-115">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fbd88-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fbd88-116">Parent elements</span></span>  
  
|<span data-ttu-id="fbd88-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="fbd88-117">Element</span></span>|<span data-ttu-id="fbd88-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbd88-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="fbd88-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.</span><span class="sxs-lookup"><span data-stu-id="fbd88-119">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fbd88-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbd88-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="fbd88-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="fbd88-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="fbd88-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fbd88-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
