---
description: 'Más información sobre: <workflowInstanceQueries> de WCF'
title: <workflowInstanceQueries> de WCF
ms.date: 03/30/2017
ms.assetid: b0852f77-16e4-4d55-8eb7-a19feb0e8fc4
ms.openlocfilehash: d4dc4827cba5a1732070b5269350ca3dd9bf2c47
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682337"
---
# <a name="workflowinstancequeries-of-wcf"></a><span data-ttu-id="587a5-103">\<workflowInstanceQueries> de WCF</span><span class="sxs-lookup"><span data-stu-id="587a5-103">\<workflowInstanceQueries> of WCF</span></span>

<span data-ttu-id="587a5-104">Representa una colección de elementos de configuración que realizan el seguimiento de los cambios del ciclo de vida de la instancia del flujo de trabajo, como un evento iniciado o completado.</span><span class="sxs-lookup"><span data-stu-id="587a5-104">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
<span data-ttu-id="587a5-105">Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .</span><span class="sxs-lookup"><span data-stu-id="587a5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowInstanceQueries>**  
  
## <a name="syntax"></a><span data-ttu-id="587a5-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="587a5-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="587a5-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="587a5-107">Attributes and elements</span></span>

<span data-ttu-id="587a5-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="587a5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="587a5-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="587a5-109">Attributes</span></span>  

<span data-ttu-id="587a5-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="587a5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="587a5-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="587a5-111">Child elements</span></span>  
  
|<span data-ttu-id="587a5-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="587a5-112">Element</span></span>|<span data-ttu-id="587a5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="587a5-113">Description</span></span>|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](workflowinstancequery-of-wcf.md)|<span data-ttu-id="587a5-114">Una consulta que se utiliza para realizar el seguimiento de los cambios de ciclo de vida de la instancia del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="587a5-114">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="587a5-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="587a5-115">Parent elements</span></span>  
  
|<span data-ttu-id="587a5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="587a5-116">Element</span></span>|<span data-ttu-id="587a5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="587a5-117">Description</span></span>|  
|-------------|-----------------|  
|[\<workflow>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="587a5-118">Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) .</span><span class="sxs-lookup"><span data-stu-id="587a5-118">A configuration element that contains all queries for a specific workflow identified by the [activityDefinitionId](xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId) property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="587a5-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="587a5-119">Remarks</span></span>

<span data-ttu-id="587a5-120"><xref:System.Activities.Tracking.WorkflowInstanceQuery> se usa para suscribirse a los siguientes objetos <xref:System.Activities.Tracking.TrackingRecord>:</span><span class="sxs-lookup"><span data-stu-id="587a5-120">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
- <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="587a5-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="587a5-121">Example</span></span>  

<span data-ttu-id="587a5-122">La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.</span><span class="sxs-lookup"><span data-stu-id="587a5-122">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="587a5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="587a5-123">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="587a5-124">Seguimiento y traza del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="587a5-124">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="587a5-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="587a5-125">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
