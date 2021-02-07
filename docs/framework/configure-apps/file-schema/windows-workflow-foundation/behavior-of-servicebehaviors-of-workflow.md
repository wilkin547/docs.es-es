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
# <a name="behavior-of-servicebehaviors-of-workflow"></a>\<behavior> de \<serviceBehaviors> de flujo de trabajo

El elemento **Behavior** contiene una colección de valores para el comportamiento de un servicio. Cada comportamiento se indexa por su **nombre**. Los servicios se pueden vincular a cada comportamiento a través de este nombre mediante el atributo **behaviorConfiguration** del [\<endpoint>](../wcf/endpoint-element.md) elemento. De esta forma, los extremos pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**  
  
## <a name="syntax"></a>Sintaxis  
  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento. Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<bufferReceive>](bufferreceive.md)|Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.|  
|[\<routing>](../wcf/routing-of-servicebehavior.md)|Un comportamiento del servicio que permite a un servicio usar el seguimiento de ETW utilizando un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant>.|  
|[\<sendMessageChannelCache>](sendmessagechannelcache.md)|Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.|  
|[\<sqlWorkflowInstanceStore>](sqlworkflowinstancestore.md)|Un comportamiento del servicio que permite configurar la característica <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, que admite la conservación de la información de estado de las instancias del servicio de flujo de trabajo en una base de datos SQL Server 2005 o SQL Server 2008.|  
|[\<workflowIdle>](workflowidle.md)|Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.|  
|[\<workflowInstanceManagement>](workflowinstancemanagement.md)|Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.|  
|[\<workflowUnhandledException>](workflowunhandledexception.md)|Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors-of-workflow.md)|Colección de elementos de comportamiento del servicio.|
