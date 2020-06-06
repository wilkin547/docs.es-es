---
title: <> System. serviceModel del flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79151954"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="37c67-102">\<system.serviceModel>del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="37c67-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="37c67-103">Esta sección de configuración contiene todos los elementos de configuración del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c67-103">This configuration section contains all the workflow configuration elements.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.ServiceModel>**  
  
## <a name="syntax"></a><span data-ttu-id="37c67-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37c67-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37c67-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="37c67-105">Attributes and Elements</span></span>  
 <span data-ttu-id="37c67-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="37c67-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37c67-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="37c67-107">Attributes</span></span>  
 <span data-ttu-id="37c67-108">None</span><span class="sxs-lookup"><span data-stu-id="37c67-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37c67-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="37c67-109">Child Elements</span></span>  
  
|<span data-ttu-id="37c67-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="37c67-110">Element</span></span>|<span data-ttu-id="37c67-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="37c67-111">Description</span></span>|  
|-------------|-----------------|  
|[\<behaviors>](behaviors-of-workflow.md)|<span data-ttu-id="37c67-112">En esta sección se define la colección **serviceBehaviors** .</span><span class="sxs-lookup"><span data-stu-id="37c67-112">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="37c67-113">Cada elemento de la colección define elementos de comportamiento utilizados por los servicios.</span><span class="sxs-lookup"><span data-stu-id="37c67-113">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="37c67-114">Cada elemento de comportamiento se identifica mediante su atributo de **nombre** único.</span><span class="sxs-lookup"><span data-stu-id="37c67-114">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[\<tracking>](tracking.md)|<span data-ttu-id="37c67-115">Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="37c67-115">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="37c67-116">Para obtener más información sobre el seguimiento del flujo de trabajo y su configuración, consulte [seguimiento y](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) seguimiento del flujo de trabajo y [configuración del seguimiento para un flujo de trabajo](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="37c67-116">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37c67-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="37c67-117">Parent Elements</span></span>  
  
|<span data-ttu-id="37c67-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="37c67-118">Element</span></span>|<span data-ttu-id="37c67-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="37c67-119">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="37c67-120">El elemento raíz para todos los elementos de configuración en un archivo de configuración .NET.</span><span class="sxs-lookup"><span data-stu-id="37c67-120">The root element for all configuration elements in a .NET configuration file.</span></span>|
