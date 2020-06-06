---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152292"
---
# \<cancelRequestedQuery>
<span data-ttu-id="54983-101">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="54983-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="54983-102">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="54983-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="54983-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="54983-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="54983-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54983-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54983-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="54983-105">Attributes and Elements</span></span>  
 <span data-ttu-id="54983-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="54983-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54983-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="54983-107">Attributes</span></span>  
  
|<span data-ttu-id="54983-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="54983-108">Attribute</span></span>|<span data-ttu-id="54983-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="54983-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="54983-110">activityName</span><span class="sxs-lookup"><span data-stu-id="54983-110">activityName</span></span>|<span data-ttu-id="54983-111">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="54983-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="54983-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="54983-112">childActivityName</span></span>|<span data-ttu-id="54983-113">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="54983-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54983-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="54983-114">Child Elements</span></span>  
 <span data-ttu-id="54983-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="54983-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54983-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="54983-116">Parent Elements</span></span>  
  
|<span data-ttu-id="54983-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="54983-117">Element</span></span>|<span data-ttu-id="54983-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="54983-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="54983-119">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="54983-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="54983-120">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="54983-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54983-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54983-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="54983-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="54983-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="54983-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="54983-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
