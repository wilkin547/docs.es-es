---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: a50e9965a595fce64c383313091334e883dcfbfa
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189492"
---
# \<cancelRequestedQuery>

<span data-ttu-id="79ac8-101">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="79ac8-101">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="79ac8-102">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="79ac8-102">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="79ac8-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="79ac8-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="79ac8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79ac8-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79ac8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79ac8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="79ac8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79ac8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79ac8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="79ac8-107">Attributes</span></span>  
  
|<span data-ttu-id="79ac8-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="79ac8-108">Attribute</span></span>|<span data-ttu-id="79ac8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ac8-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79ac8-110">activityName</span><span class="sxs-lookup"><span data-stu-id="79ac8-110">activityName</span></span>|<span data-ttu-id="79ac8-111">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="79ac8-111">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="79ac8-112">childActivityName</span><span class="sxs-lookup"><span data-stu-id="79ac8-112">childActivityName</span></span>|<span data-ttu-id="79ac8-113">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="79ac8-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79ac8-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79ac8-114">Child Elements</span></span>  

 <span data-ttu-id="79ac8-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="79ac8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79ac8-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79ac8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="79ac8-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="79ac8-117">Element</span></span>|<span data-ttu-id="79ac8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ac8-118">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="79ac8-119">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="79ac8-119">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="79ac8-120">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="79ac8-120">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79ac8-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79ac8-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="79ac8-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="79ac8-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="79ac8-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="79ac8-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
