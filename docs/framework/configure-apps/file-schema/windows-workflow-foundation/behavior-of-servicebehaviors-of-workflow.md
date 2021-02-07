---
description: 'Más información sobre: <behavior> de <serviceBehaviors> de flujo de trabajo'
title: <behavior> de <serviceBehaviors> de flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 7504e9b307286871440bb6efdb672a59d3d13cb1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725290"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="7038f-103">\<behavior> de \<serviceBehaviors> de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7038f-103">\<behavior> of \<serviceBehaviors> of workflow</span></span>

<span data-ttu-id="7038f-104">El elemento **Behavior** contiene una colección de valores para el comportamiento de un servicio.</span><span class="sxs-lookup"><span data-stu-id="7038f-104">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="7038f-105">Cada comportamiento se indexa por su **nombre**.</span><span class="sxs-lookup"><span data-stu-id="7038f-105">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="7038f-106">Los servicios se pueden vincular a cada comportamiento a través de este nombre mediante el atributo **behaviorConfiguration** del [\<endpoint>](../wcf/endpoint-element.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="7038f-106">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="7038f-107">De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.</span><span class="sxs-lookup"><span data-stu-id="7038f-107">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a><span data-ttu-id="7038f-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7038f-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7038f-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="7038f-109">Attributes and Elements</span></span>  

 <span data-ttu-id="7038f-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="7038f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7038f-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="7038f-111">Attributes</span></span>  
  
|<span data-ttu-id="7038f-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="7038f-112">Attribute</span></span>|<span data-ttu-id="7038f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="7038f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7038f-114">name</span><span class="sxs-lookup"><span data-stu-id="7038f-114">name</span></span>|<span data-ttu-id="7038f-115">Una cadena única que contiene el nombre de la configuración del comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7038f-115">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="7038f-116">Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.</span><span class="sxs-lookup"><span data-stu-id="7038f-116">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7038f-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="7038f-117">Child Elements</span></span>  
  
|<span data-ttu-id="7038f-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="7038f-118">Element</span></span>|<span data-ttu-id="7038f-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="7038f-119">Description</span></span>|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|<span data-ttu-id="7038f-120">Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.</span><span class="sxs-lookup"><span data-stu-id="7038f-120">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="7038f-121">Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="7038f-121">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|<span data-ttu-id="7038f-122">Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.</span><span class="sxs-lookup"><span data-stu-id="7038f-122">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|<span data-ttu-id="7038f-123">Un comportamiento del servicio que permite configurar la característica <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, que admite la conservación de la información de estado de las instancias del servicio de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="7038f-123">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[\<workflowIdle>](workflowidle.md)|<span data-ttu-id="7038f-124">Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.</span><span class="sxs-lookup"><span data-stu-id="7038f-124">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|<span data-ttu-id="7038f-125">Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.</span><span class="sxs-lookup"><span data-stu-id="7038f-125">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|<span data-ttu-id="7038f-126">Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7038f-126">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7038f-127">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="7038f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="7038f-128">Elemento</span><span class="sxs-lookup"><span data-stu-id="7038f-128">Element</span></span>|<span data-ttu-id="7038f-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="7038f-129">Description</span></span>|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|<span data-ttu-id="7038f-130">Colección de elementos de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="7038f-130">A collection of service behavior elements.</span></span>|
