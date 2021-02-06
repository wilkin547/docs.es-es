---
description: 'Más información sobre: <cancelRequestedQuery> de WCF'
title: <cancelRequestedQuery> de WCF
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: e477e33650eb901cf2e9275570d8538196c52b6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639177"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="a865e-103">\<cancelRequestedQuery> de WCF</span><span class="sxs-lookup"><span data-stu-id="a865e-103">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="a865e-104">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="a865e-104">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a865e-105">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="a865e-105">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="a865e-106">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a865e-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  

## <a name="syntax"></a><span data-ttu-id="a865e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a865e-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a865e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a865e-108">Attributes and elements</span></span>

<span data-ttu-id="a865e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a865e-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a865e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="a865e-110">Attributes</span></span>  
  
|<span data-ttu-id="a865e-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="a865e-111">Attribute</span></span>|<span data-ttu-id="a865e-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a865e-112">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="a865e-113">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="a865e-113">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="a865e-114">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="a865e-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a865e-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a865e-115">Child elements</span></span>

<span data-ttu-id="a865e-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a865e-116">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="a865e-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a865e-117">Parent elements</span></span>
  
|<span data-ttu-id="a865e-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a865e-118">Element</span></span>|<span data-ttu-id="a865e-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a865e-119">Description</span></span>|  
|-------------|-----------------|  
|[\<cancelRequestedQueries>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="a865e-120">Representa una colección de consultas que se usan para realizar el seguimiento de las solicitudes para cancelar una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="a865e-120">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a865e-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a865e-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a865e-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a865e-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a865e-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a865e-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
