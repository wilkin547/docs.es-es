---
title: '&lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 81dfde9a4b75caeea263cc0809f450cbc0c9a5e9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="7a973-102">&lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7a973-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="7a973-103">El **comportamiento** elemento contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="7a973-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="7a973-104">Cada comportamiento se indiza por su **nombre**.</span><span class="sxs-lookup"><span data-stu-id="7a973-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="7a973-105">Servicios pueden vincularse a cada comportamiento a través de este nombre mediante la **behaviorConfiguration**atributo de la [ \<extremo >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7a973-105">Services can link to each behavior through this name using the **behaviorConfiguration**attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="7a973-106">De esta forma, los puntos de conexión pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="7a973-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="7a973-107">\<sistema. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7a973-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="7a973-108">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="7a973-108">\<behaviors></span></span>  
<span data-ttu-id="7a973-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7a973-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="7a973-110">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="7a973-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a973-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a973-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  honstLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a973-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7a973-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7a973-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7a973-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a973-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="7a973-114">Attributes</span></span>  
  
|<span data-ttu-id="7a973-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="7a973-115">Attribute</span></span>|<span data-ttu-id="7a973-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a973-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a973-117">name</span><span class="sxs-lookup"><span data-stu-id="7a973-117">name</span></span>|<span data-ttu-id="7a973-118">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7a973-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="7a973-119">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="7a973-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a973-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7a973-120">Child Elements</span></span>  
  
|<span data-ttu-id="7a973-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a973-121">Element</span></span>|<span data-ttu-id="7a973-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a973-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a973-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="7a973-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="7a973-124">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="7a973-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="7a973-125">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="7a973-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="7a973-126">Un comportamiento de servicio que permite que un servicio utilizar el seguimiento de ETW mediante un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="7a973-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="7a973-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="7a973-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="7a973-128">Un comportamiento de servicio que permite la personalización de la memoria caché de uso compartido de niveles, la configuración de la memoria de caché del generador de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a extremos de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="7a973-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="7a973-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="7a973-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="7a973-130">Un comportamiento del servicio que le permite configurar el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> característica, que admite conservar información de estado para instancias de servicio de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7a973-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="7a973-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="7a973-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="7a973-132">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="7a973-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="7a973-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="7a973-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="7a973-134">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="7a973-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="7a973-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="7a973-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="7a973-136">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7a973-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7a973-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7a973-137">Parent Elements</span></span>  
  
|<span data-ttu-id="7a973-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="7a973-138">Element</span></span>|<span data-ttu-id="7a973-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a973-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a973-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7a973-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="7a973-141">Colección de elementos de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="7a973-141">A collection of service behavior elements.</span></span>|
