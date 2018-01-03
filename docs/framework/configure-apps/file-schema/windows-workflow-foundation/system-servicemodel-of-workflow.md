---
title: '&lt;system.serviceModel&gt; de flujo de trabajo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54f8ae10491ebeed683a2ec289e60b9a90afd43b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="4daef-102">&lt;system.serviceModel&gt; de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="4daef-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="4daef-103">Esta sección de configuración contiene todos los elementos de configuración del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4daef-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4daef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4daef-104">Syntax</span></span>  
  
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
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4daef-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4daef-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4daef-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4daef-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4daef-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4daef-107">Attributes</span></span>  
 <span data-ttu-id="4daef-108">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4daef-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4daef-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4daef-109">Child Elements</span></span>  
  
|<span data-ttu-id="4daef-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="4daef-110">Element</span></span>|<span data-ttu-id="4daef-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4daef-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4daef-112">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="4daef-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="4daef-113">Esta sección define la **serviceBehaviors** colección.</span><span class="sxs-lookup"><span data-stu-id="4daef-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="4daef-114">Cada elemento de la colección define elementos de comportamiento utilizados por los servicios.</span><span class="sxs-lookup"><span data-stu-id="4daef-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="4daef-115">Su único identifica cada elemento de comportamiento **nombre** atributo.</span><span class="sxs-lookup"><span data-stu-id="4daef-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="4daef-116">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="4daef-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="4daef-117">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4daef-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="4daef-118">Para obtener más información del seguimiento de flujo de trabajo y su configuración, consulte [seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) y [configuración del seguimiento para un flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="4daef-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4daef-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4daef-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4daef-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="4daef-120">Element</span></span>|<span data-ttu-id="4daef-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="4daef-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4daef-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4daef-122">\<configuration></span></span>|<span data-ttu-id="4daef-123">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="4daef-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
