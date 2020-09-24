---
title: <workflowInstanceQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
ms.openlocfilehash: 1b1315aa176f26c356726c5edf1c851bb4c63a47
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148613"
---
# \<workflowInstanceQueries>

<span data-ttu-id="24e3e-101">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="24e3e-101">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="24e3e-102">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="24e3e-102">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="24e3e-103">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24e3e-103">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24e3e-104">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="24e3e-104">Attributes and Elements</span></span>  

<span data-ttu-id="24e3e-105">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="24e3e-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24e3e-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="24e3e-106">Attributes</span></span>  

<span data-ttu-id="24e3e-107">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="24e3e-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="24e3e-108">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="24e3e-108">Child Elements</span></span>  
  
|<span data-ttu-id="24e3e-109">Elemento</span><span class="sxs-lookup"><span data-stu-id="24e3e-109">Element</span></span>|<span data-ttu-id="24e3e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="24e3e-110">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery.md)|<span data-ttu-id="24e3e-111">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="24e3e-111">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="24e3e-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="24e3e-112">Parent Elements</span></span>  
  
|<span data-ttu-id="24e3e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="24e3e-113">Element</span></span>|<span data-ttu-id="24e3e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="24e3e-114">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](workflow.md)|<span data-ttu-id="24e3e-115">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId** .</span><span class="sxs-lookup"><span data-stu-id="24e3e-115">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24e3e-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="24e3e-116">Remarks</span></span>  

<span data-ttu-id="24e3e-117"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="24e3e-117">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="24e3e-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="24e3e-118">Example</span></span>  

<span data-ttu-id="24e3e-119">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="24e3e-119">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24e3e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e3e-120">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="24e3e-121">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="24e3e-121">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="24e3e-122">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="24e3e-122">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
