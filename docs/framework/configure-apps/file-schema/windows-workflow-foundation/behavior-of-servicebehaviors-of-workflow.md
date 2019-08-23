---
title: <behavior>de <serviceBehaviors> de flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946078"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="676f4-102">\<comportamiento > de \<serviceBehaviors > de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="676f4-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="676f4-103">El elemento **Behavior** contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="676f4-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="676f4-104">Cada comportamiento se indexa por su **nombre**.</span><span class="sxs-lookup"><span data-stu-id="676f4-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="676f4-105">Los servicios se pueden vincular a cada comportamiento a través de este nombre mediante el atributo **behaviorConfiguration** del [ \<punto de conexión >](../wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="676f4-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="676f4-106">De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="676f4-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="676f4-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="676f4-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="676f4-108">\<comportamientos ></span><span class="sxs-lookup"><span data-stu-id="676f4-108">\<behaviors></span></span>  
<span data-ttu-id="676f4-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="676f4-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="676f4-110">\<comportamiento ></span><span class="sxs-lookup"><span data-stu-id="676f4-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676f4-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="676f4-111">Syntax</span></span>  
  
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
                                  hostLockRenewalPeriod="TimeSpan" 
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="676f4-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="676f4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="676f4-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="676f4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="676f4-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="676f4-114">Attributes</span></span>  
  
|<span data-ttu-id="676f4-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="676f4-115">Attribute</span></span>|<span data-ttu-id="676f4-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="676f4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="676f4-117">Nombre</span><span class="sxs-lookup"><span data-stu-id="676f4-117">name</span></span>|<span data-ttu-id="676f4-118">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="676f4-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="676f4-119">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="676f4-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="676f4-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="676f4-120">Child Elements</span></span>  
  
|<span data-ttu-id="676f4-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="676f4-121">Element</span></span>|<span data-ttu-id="676f4-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="676f4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="676f4-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="676f4-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="676f4-124">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="676f4-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="676f4-125">\<> de enrutamiento</span><span class="sxs-lookup"><span data-stu-id="676f4-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="676f4-126">Un comportamiento del servicio que permite a un servicio usar el seguimiento de <xref:System.Activities.Tracking.EtwTrackingParticipant>ETW mediante.</span><span class="sxs-lookup"><span data-stu-id="676f4-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="676f4-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="676f4-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="676f4-128">Un comportamiento del servicio que permite la personalización de los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la configuración de la memoria caché del canal para los flujos de trabajo que envían mensajes a los puntos de conexión de servicio mediante el envío de actividades de mensajería.</span><span class="sxs-lookup"><span data-stu-id="676f4-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="676f4-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="676f4-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="676f4-130">Un comportamiento del servicio que permite configurar la característica <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> , que admite la persistencia de la información de estado de las instancias del servicio de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="676f4-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="676f4-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="676f4-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="676f4-132">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="676f4-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="676f4-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="676f4-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="676f4-134">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="676f4-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="676f4-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="676f4-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="676f4-136">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="676f4-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="676f4-137">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="676f4-137">Parent Elements</span></span>  
  
|<span data-ttu-id="676f4-138">Elemento</span><span class="sxs-lookup"><span data-stu-id="676f4-138">Element</span></span>|<span data-ttu-id="676f4-139">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="676f4-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="676f4-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="676f4-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="676f4-141">Colección de elementos de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="676f4-141">A collection of service behavior elements.</span></span>|
