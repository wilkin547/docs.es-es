---
title: <workflowInstanceQueries>de WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: 8a58767745efab67fb7550de8770fec2c6226117
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854775"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="6d5b6-102">\<workflowInstanceQueries>de WCF</span><span class="sxs-lookup"><span data-stu-id="6d5b6-102">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="6d5b6-103">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="6d5b6-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="6d5b6-104">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="6d5b6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="6d5b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d5b6-105">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6d5b6-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6d5b6-106">Attributes and elements</span></span>

<span data-ttu-id="6d5b6-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6d5b6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6d5b6-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="6d5b6-108">Attributes</span></span>  

<span data-ttu-id="6d5b6-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6d5b6-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6d5b6-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6d5b6-110">Child elements</span></span>  
  
|<span data-ttu-id="6d5b6-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d5b6-111">Element</span></span>|<span data-ttu-id="6d5b6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d5b6-112">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="6d5b6-113">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6d5b6-113">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6d5b6-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6d5b6-114">Parent elements</span></span>  
  
|<span data-ttu-id="6d5b6-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="6d5b6-115">Element</span></span>|<span data-ttu-id="6d5b6-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="6d5b6-116">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="6d5b6-117">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="6d5b6-117">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6d5b6-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d5b6-118">Remarks</span></span>

<span data-ttu-id="6d5b6-119"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="6d5b6-119">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="6d5b6-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d5b6-120">Example</span></span>  

<span data-ttu-id="6d5b6-121">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="6d5b6-121">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="6d5b6-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6d5b6-122">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6d5b6-123">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="6d5b6-123">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6d5b6-124">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6d5b6-124">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
