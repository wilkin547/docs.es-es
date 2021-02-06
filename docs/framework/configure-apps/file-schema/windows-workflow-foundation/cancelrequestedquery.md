---
description: 'Más información acerca de: <cancelRequestedQuery>'
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: efd908fb52d2bc32bf05fce9099c7105abdc9b1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652645"
---
# \<cancelRequestedQuery>

<span data-ttu-id="53ca5-102">Representa una consulta que se usa para realizar un seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="53ca5-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="53ca5-103">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="53ca5-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="53ca5-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="53ca5-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="53ca5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53ca5-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53ca5-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="53ca5-106">Attributes and Elements</span></span>  

 <span data-ttu-id="53ca5-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="53ca5-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53ca5-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="53ca5-108">Attributes</span></span>  
  
|<span data-ttu-id="53ca5-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="53ca5-109">Attribute</span></span>|<span data-ttu-id="53ca5-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="53ca5-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="53ca5-111">activityName</span><span class="sxs-lookup"><span data-stu-id="53ca5-111">activityName</span></span>|<span data-ttu-id="53ca5-112">Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.</span><span class="sxs-lookup"><span data-stu-id="53ca5-112">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="53ca5-113">childActivityName</span><span class="sxs-lookup"><span data-stu-id="53ca5-113">childActivityName</span></span>|<span data-ttu-id="53ca5-114">Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.</span><span class="sxs-lookup"><span data-stu-id="53ca5-114">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="53ca5-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="53ca5-115">Child Elements</span></span>  

 <span data-ttu-id="53ca5-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="53ca5-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="53ca5-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="53ca5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="53ca5-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="53ca5-118">Element</span></span>|<span data-ttu-id="53ca5-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="53ca5-119">Description</span></span>|  
|-------------|-----------------|  
|[\<faultPropagationQuery>](faultpropagationquery.md)|<span data-ttu-id="53ca5-120">Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.</span><span class="sxs-lookup"><span data-stu-id="53ca5-120">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="53ca5-121">La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.</span><span class="sxs-lookup"><span data-stu-id="53ca5-121">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53ca5-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ca5-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="53ca5-123">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="53ca5-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="53ca5-124">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="53ca5-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
