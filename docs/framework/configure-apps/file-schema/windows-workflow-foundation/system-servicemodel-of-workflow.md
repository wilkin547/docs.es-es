---
title: < system.serviceModel > de flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 5580bf570c4c728b526bd62109b48c3ccc18943a
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422885"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="3dae6-102">\<system.serviceModel > de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="3dae6-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="3dae6-103">Esta sección de configuración contiene todos los elementos de configuración del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3dae6-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dae6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3dae6-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName="String"   
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>    
     <participants>   
      <add name="String"   
           profileName="String"  
           type="String" />   
     </participants>   
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dae6-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3dae6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3dae6-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3dae6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dae6-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="3dae6-107">Attributes</span></span>  
 <span data-ttu-id="3dae6-108">Ninguna</span><span class="sxs-lookup"><span data-stu-id="3dae6-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3dae6-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3dae6-109">Child Elements</span></span>  
  
|<span data-ttu-id="3dae6-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dae6-110">Element</span></span>|<span data-ttu-id="3dae6-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dae6-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dae6-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="3dae6-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="3dae6-113">Esta sección se define la **serviceBehaviors** colección.</span><span class="sxs-lookup"><span data-stu-id="3dae6-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="3dae6-114">Cada elemento de la colección define elementos de comportamiento utilizados por los servicios.</span><span class="sxs-lookup"><span data-stu-id="3dae6-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="3dae6-115">Su único identifica cada elemento de comportamiento **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="3dae6-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="3dae6-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3dae6-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="3dae6-117">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3dae6-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="3dae6-118">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [configuración del seguimiento para un flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="3dae6-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3dae6-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3dae6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3dae6-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="3dae6-120">Element</span></span>|<span data-ttu-id="3dae6-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="3dae6-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3dae6-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3dae6-122">\<configuration></span></span>|<span data-ttu-id="3dae6-123">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="3dae6-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
