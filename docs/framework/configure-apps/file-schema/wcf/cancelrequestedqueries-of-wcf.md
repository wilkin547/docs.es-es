---
title: <cancelRequestedQueries>de WCF
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850098"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="85615-102">\<cancelRequestedQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="85615-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="85615-103">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="85615-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="85615-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="85615-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="85615-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="85615-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="85615-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85615-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85615-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="85615-107">Attributes and elements</span></span>  

<span data-ttu-id="85615-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="85615-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85615-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="85615-109">Attributes</span></span>

<span data-ttu-id="85615-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="85615-110">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="85615-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="85615-111">Child elements</span></span>
  
|<span data-ttu-id="85615-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="85615-112">Element</span></span>|<span data-ttu-id="85615-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="85615-113">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="85615-114">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="85615-114">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85615-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="85615-115">Parent elements</span></span>  
  
|<span data-ttu-id="85615-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="85615-116">Element</span></span>|<span data-ttu-id="85615-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="85615-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="85615-118">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId>.</span><span class="sxs-lookup"><span data-stu-id="85615-118">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="85615-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="85615-119">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="85615-120">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="85615-120">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="85615-121">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="85615-121">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
