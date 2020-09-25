---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 4db30f3fed12b585b73339120fa5bc6602150e7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189544"
---
# \<cancelRequestedQueries>

<span data-ttu-id="50753-101">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="50753-101">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="50753-102">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="50753-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="50753-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="50753-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="50753-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50753-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50753-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="50753-105">Attributes and Elements</span></span>  

 <span data-ttu-id="50753-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="50753-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50753-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="50753-107">Attributes</span></span>  

 <span data-ttu-id="50753-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="50753-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="50753-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="50753-109">Child Elements</span></span>  
  
|<span data-ttu-id="50753-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="50753-110">Element</span></span>|<span data-ttu-id="50753-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="50753-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](cancelrequestedquery.md)|<span data-ttu-id="50753-112">Una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="50753-112">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="50753-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="50753-113">Parent Elements</span></span>  
  
|<span data-ttu-id="50753-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="50753-114">Element</span></span>|<span data-ttu-id="50753-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="50753-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="50753-116">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="50753-116">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50753-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="50753-117">See also</span></span>

- [<span data-ttu-id="50753-118">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="50753-118">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="50753-119">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="50753-119">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
