---
title: <system.serviceModel> del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151954"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="c9900-102">\<system.serviceModel> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c9900-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="c9900-103">Esta sección de configuración contiene todos los elementos de configuración del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c9900-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="c9900-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c9900-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c9900-105">&nbsp;&nbsp;**\<Sistema.>De ServiceModel**</span><span class="sxs-lookup"><span data-stu-id="c9900-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9900-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9900-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9900-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c9900-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c9900-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c9900-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9900-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="c9900-109">Attributes</span></span>  
 <span data-ttu-id="c9900-110">None</span><span class="sxs-lookup"><span data-stu-id="c9900-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9900-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c9900-111">Child Elements</span></span>  
  
|<span data-ttu-id="c9900-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9900-112">Element</span></span>|<span data-ttu-id="c9900-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9900-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9900-114">\<comportamientos></span><span class="sxs-lookup"><span data-stu-id="c9900-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="c9900-115">En esta sección se define la colección **serviceBehaviors.**</span><span class="sxs-lookup"><span data-stu-id="c9900-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="c9900-116">Cada elemento de la colección define elementos de comportamiento utilizados por los servicios.</span><span class="sxs-lookup"><span data-stu-id="c9900-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="c9900-117">Cada elemento de comportamiento se identifica por su atributo **de nombre** único.</span><span class="sxs-lookup"><span data-stu-id="c9900-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="c9900-118">\<seguimiento></span><span class="sxs-lookup"><span data-stu-id="c9900-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="c9900-119">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c9900-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="c9900-120">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, vea [Seguimiento y seguimiento](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) del flujo de trabajo y Configuración del seguimiento de un flujo de [trabajo](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="c9900-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9900-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c9900-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c9900-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="c9900-122">Element</span></span>|<span data-ttu-id="c9900-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9900-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9900-124">\<configuración></span><span class="sxs-lookup"><span data-stu-id="c9900-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="c9900-125">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="c9900-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
