---
description: 'Más información sobre: <cancelRequestedQueries> de WCF'
title: <cancelRequestedQueries> de WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 3850d7efd01f9092312567a0eba68a6e9547baad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639190"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="ddfc2-103">\<cancelRequestedQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="ddfc2-103">\<cancelRequestedQueries> of WCF</span></span>

<span data-ttu-id="ddfc2-104">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-104">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ddfc2-105">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-105">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="ddfc2-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="ddfc2-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="ddfc2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddfc2-107">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddfc2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ddfc2-108">Attributes and elements</span></span>  

<span data-ttu-id="ddfc2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddfc2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ddfc2-110">Attributes</span></span>

<span data-ttu-id="ddfc2-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-111">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="ddfc2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ddfc2-112">Child elements</span></span>
  
|<span data-ttu-id="ddfc2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddfc2-113">Element</span></span>|<span data-ttu-id="ddfc2-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddfc2-114">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="ddfc2-115">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-115">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ddfc2-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ddfc2-116">Parent elements</span></span>  
  
|<span data-ttu-id="ddfc2-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ddfc2-117">Element</span></span>|<span data-ttu-id="ddfc2-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddfc2-118">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="ddfc2-119">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="ddfc2-119">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ddfc2-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddfc2-120">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="ddfc2-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ddfc2-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ddfc2-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ddfc2-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
