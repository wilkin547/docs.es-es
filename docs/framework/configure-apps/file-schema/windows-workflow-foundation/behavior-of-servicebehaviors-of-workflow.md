---
title: "&lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;comportamiento&gt; de &lt;serviceBehaviors&gt; de flujo de trabajo
El elemento **behavior** contiene una colección de valores para el comportamiento de un servicio.  Su **name** indiza cada comportamiento.  Los servicios pueden vincularse a cada comportamiento a través de este nombre mediante el atributo **behaviorConfiguration** del elemento [\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md).  De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.  
  
## Sintaxis  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name=String">  
      <bufferReceive maxPendingMessagesPerChannel=”Integer” />  
      <etwTracking profileName=”String” />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore   
          connectionStringName=”String”   
          honstLockRenewalPeriod=”TimeSpan”  
          instanceCompletionAction=”DeleteNothing/DeleteAll”  
          instanceEncodingAction=”None/GZip”  
          instanceLockedExceptionAction=”NoRetry/BasicRetry/AggressiveRetry”  
          runnableInstancesDetectionPeriod=”TimeSpan” />  
      <workflowIdle timeToPersist=”TimeSpan”  
          timeToUnload=”TimeSpan” />  
      <workflowUnhandledException action=”Abandon/AbandonAndSuspend/Cancel/Terminate” />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento.  Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<bufferReceive\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.|  
|[\<enrutar\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.ETWTrackingParticipant>.|  
|[\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.|  
|[\<sqlWorkflowInstanceStore\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|Un comportamiento del servicio que permite configurar la característica <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, que admite la conservación de la información de estado de las instancias del servicio de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008.|  
|[\<workflowIdle\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.|  
|[\<workflowInstanceManagement\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.|  
|[\<workflowUnhandledException\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Colección de elementos de comportamiento del servicio.|