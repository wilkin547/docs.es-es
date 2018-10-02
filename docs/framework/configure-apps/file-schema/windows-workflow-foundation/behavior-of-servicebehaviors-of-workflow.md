---
title: '&lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 9b16aad6138d79d3dbff4994250f05d617d54140
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035901"
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a><span data-ttu-id="854e5-102">&lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="854e5-102">&lt;behavior&gt; of &lt;serviceBehaviors&gt; of workflow</span></span>
<span data-ttu-id="854e5-103">El **comportamiento** elemento contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="854e5-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="854e5-104">Indiza cada comportamiento su **nombre**.</span><span class="sxs-lookup"><span data-stu-id="854e5-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="854e5-105">Servicios pueden vincularse a cada comportamiento a través de este nombre mediante el **behaviorConfiguration** atributo de la [ \<punto de conexión >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="854e5-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="854e5-106">De esta forma, los puntos de conexión pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="854e5-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="854e5-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="854e5-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="854e5-108">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="854e5-108">\<behaviors></span></span>  
<span data-ttu-id="854e5-109">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="854e5-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="854e5-110">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="854e5-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="854e5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="854e5-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="854e5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="854e5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="854e5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="854e5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="854e5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="854e5-114">Attributes</span></span>  
  
|<span data-ttu-id="854e5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="854e5-115">Attribute</span></span>|<span data-ttu-id="854e5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="854e5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="854e5-117">name</span><span class="sxs-lookup"><span data-stu-id="854e5-117">name</span></span>|<span data-ttu-id="854e5-118">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="854e5-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="854e5-119">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="854e5-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="854e5-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="854e5-120">Child Elements</span></span>  
  
|<span data-ttu-id="854e5-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="854e5-121">Element</span></span>|<span data-ttu-id="854e5-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="854e5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="854e5-123">\<bufferReceive ></span><span class="sxs-lookup"><span data-stu-id="854e5-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="854e5-124">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="854e5-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="854e5-125">\<enrutamiento ></span><span class="sxs-lookup"><span data-stu-id="854e5-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="854e5-126">Un comportamiento del servicio que permite que un servicio usar el seguimiento de ETW utilizando un <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="854e5-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="854e5-127">\<sendMessageChannelCache ></span><span class="sxs-lookup"><span data-stu-id="854e5-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="854e5-128">Un comportamiento de servicio que permite la personalización de la memoria caché compartida niveles, la configuración de la memoria caché de fábrica de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a puntos de conexión de servicio mediante actividades de mensajería de envío.</span><span class="sxs-lookup"><span data-stu-id="854e5-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="854e5-129">\<sqlWorkflowInstanceStore ></span><span class="sxs-lookup"><span data-stu-id="854e5-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="854e5-130">Un comportamiento del servicio que le permite configurar el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> característica, que admite conservar información de estado para las instancias de servicio de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="854e5-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="854e5-131">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="854e5-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="854e5-132">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="854e5-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="854e5-133">\<workflowInstanceManagement ></span><span class="sxs-lookup"><span data-stu-id="854e5-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="854e5-134">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="854e5-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="854e5-135">\<workflowUnhandledException ></span><span class="sxs-lookup"><span data-stu-id="854e5-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="854e5-136">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="854e5-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="854e5-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="854e5-137">Parent Elements</span></span>  
  
|<span data-ttu-id="854e5-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="854e5-138">Element</span></span>|<span data-ttu-id="854e5-139">Descripción</span><span class="sxs-lookup"><span data-stu-id="854e5-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="854e5-140">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="854e5-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="854e5-141">Colección de elementos de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="854e5-141">A collection of service behavior elements.</span></span>|
