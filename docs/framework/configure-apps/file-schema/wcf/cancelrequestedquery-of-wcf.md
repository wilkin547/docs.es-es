---
title: <cancelRequestedQuery>de WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850053"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="ae5ac-102">\<cancelRequestedQuery>de WCF</span><span class="sxs-lookup"><span data-stu-id="ae5ac-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="ae5ac-103">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ae5ac-104">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="ae5ac-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ae5ac-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  

## <a name="syntax"></a><span data-ttu-id="ae5ac-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae5ac-106">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ae5ac-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ae5ac-107">Attributes and elements</span></span>

<span data-ttu-id="ae5ac-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ae5ac-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="ae5ac-109">Attributes</span></span>  
  
|<span data-ttu-id="ae5ac-110">Atributo</span><span class="sxs-lookup"><span data-stu-id="ae5ac-110">Attribute</span></span>|<span data-ttu-id="ae5ac-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae5ac-111">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="ae5ac-112">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="ae5ac-113">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-113">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ae5ac-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ae5ac-114">Child elements</span></span>

<span data-ttu-id="ae5ac-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-115">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ae5ac-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ae5ac-116">Parent elements</span></span>
  
|<span data-ttu-id="ae5ac-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="ae5ac-117">Element</span></span>|<span data-ttu-id="ae5ac-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae5ac-118">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQueries>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="ae5ac-119">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="ae5ac-119">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ae5ac-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ae5ac-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ae5ac-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ae5ac-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ae5ac-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ae5ac-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
