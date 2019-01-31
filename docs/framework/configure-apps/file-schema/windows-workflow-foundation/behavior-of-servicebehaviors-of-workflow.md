---
title: <behavior> de <serviceBehaviors> de flujo de trabajo
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 09bd54f4a7d56dc1215b1acd36ff131ba4cba12c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268267"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a>\<comportamiento > de \<serviceBehaviors > de flujo de trabajo
El **comportamiento** elemento contiene una colección de valores para el comportamiento de un servicio. Indiza cada comportamiento su **nombre**. Servicios pueden vincularse a cada comportamiento a través de este nombre mediante el **behaviorConfiguration** atributo de la [ \<punto de conexión >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento. De esta forma, los puntos de conexión pueden compartir configuraciones de comportamientos comunes sin volver a definir la configuración.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors>  
\<comportamiento >  
  
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
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|Una cadena única que contiene el nombre de la configuración del comportamiento. Este valor es una cadena definida por el usuario que debe ser única, ya que actúa como cadena de identificación del elemento.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<bufferReceive>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|Un comportamiento del servicio que permite a un servicio usar procesamiento de recepción almacenado en búfer, lo que permite que un servicio de flujo de trabajo procese mensajes desordenados.|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Un comportamiento del servicio que permite que un servicio usar el seguimiento de ETW utilizando un <xref:System.Activities.Tracking.EtwTrackingParticipant>.|  
|[\<sendMessageChannelCache>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Un comportamiento de servicio que permite la personalización de la memoria caché compartida niveles, la configuración de la memoria caché de fábrica de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a puntos de conexión de servicio mediante actividades de mensajería de envío.|  
|[\<sqlWorkflowInstanceStore>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|Un comportamiento del servicio que le permite configurar el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> característica, que admite conservar información de estado para las instancias de servicio de flujo de trabajo en una base de datos de SQL Server 2005 o SQL Server 2008.|  
|[\<workflowIdle>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|Un comportamiento del servicio que controla cuando las instancias de flujo de trabajo inactivas se descargan y conservan.|  
|[\<workflowInstanceManagement>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|Un comportamiento del servicio que permite especificar valores que controlan cómo se ejecutan las instancias de flujo de trabajo, incluida la conservación, el comportamiento de la excepción no controlada y el comportamiento inactivo.|  
|[\<workflowUnhandledException>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|Un comportamiento del servicio que permite especificar la acción que debe emprenderse cuando se produce una excepción no controlada dentro de un servicio de flujo de trabajo.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<serviceBehaviors>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|Colección de elementos de comportamiento del servicio.|
