---
description: 'Más información acerca de: <workflowInstanceQuery>'
title: <workflowInstanceQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: 39949b99e7c6c12ff8618e6aa3a43582d15d4133
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697795"
---
# \<workflowInstanceQuery>

<span data-ttu-id="9be1c-102">Representa una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="9be1c-102">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="9be1c-103">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="9be1c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQuery>**  
  
## <a name="syntax"></a><span data-ttu-id="9be1c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9be1c-104">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9be1c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9be1c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9be1c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9be1c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9be1c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9be1c-107">Attributes</span></span>  

 <span data-ttu-id="9be1c-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9be1c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9be1c-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9be1c-109">Child Elements</span></span>  
  
|<span data-ttu-id="9be1c-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="9be1c-110">Element</span></span>|<span data-ttu-id="9be1c-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9be1c-111">Description</span></span>|  
|-------------|-----------------|  
|[\<states>](states.md)|<span data-ttu-id="9be1c-112">Una colección de estados subscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9be1c-112">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9be1c-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9be1c-113">Parent Elements</span></span>  
  
|<span data-ttu-id="9be1c-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="9be1c-114">Element</span></span>|<span data-ttu-id="9be1c-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9be1c-115">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQueries>](workflowinstancequeries.md)|<span data-ttu-id="9be1c-116">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="9be1c-116">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9be1c-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9be1c-117">Remarks</span></span>  

 <span data-ttu-id="9be1c-118"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="9be1c-118">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="9be1c-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9be1c-119">Example</span></span>  

 <span data-ttu-id="9be1c-120">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="9be1c-120">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9be1c-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9be1c-121">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9be1c-122">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="9be1c-122">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9be1c-123">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="9be1c-123">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
