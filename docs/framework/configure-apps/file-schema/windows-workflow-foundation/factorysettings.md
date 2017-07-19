---
title: "&lt;factorySettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;factorySettings&gt;
Especifica los valores de la memoria caché del generador de canales.  
  
## Sintaxis  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
       <sendMessageChannelCache allowUnsafeCaching="Boolean" >          
           <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
       </sendMessageChannelCache>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|idleTimeout|Un valor TimeSpan que especifica el intervalo máximo de tiempo durante el cual el objeto puede seguir inactivo en la memoria caché antes de eliminarse.|  
|leaseTimeout|Un valor TimeSpan que especifica el intervalo de tiempo después del cual un objeto se quita de la memoria caché.|  
|maxItemsInCache|Un entero que especifica el número máximo de objetos que pueden almacenarse en la memoria caché.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|Un comportamiento del servicio que permite personalizar los niveles de uso compartido de la memoria caché, la configuración de la memoria caché del generador de canales y la de la memoria caché del canal para los flujos de trabajo que envían mensajes a los extremos de servicio utilizando las actividades de mensajería de Enviar.|  
  
## Comentarios  
 Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio.  Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.  
  
 De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> \(el almacenamiento en caché de nivel de host\).  Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo \(almacenamiento en caché en el nivel de instancia\).  El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos extremos en su configuración.  
  
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)] cómo cambiar los niveles de uso compartido  de la memoria caché y los valores de almacenamiento en la memoria caché predeterminados para el generador de canales y la memoria caché de los mismos, consulte [Cambiar los niveles de uso compartido de caché para actividades Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
## Ejemplo  
 En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación.  Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio.  En el siguiente ejemplo se muestra el contenido de un archivo de configuración que contiene el comportamiento del servicio **MyChannelCacheBehavior**  con la configuración de la memoria caché del generador personalizada y de la memoria caché del canal.  Este comportamiento del servicio se agrega al servicio a través del atributo **behaviorConfiguarion** .  
  
```  
  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>   
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>   
 <xref:System.ServiceModel.Activities.Send>   
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>   
 [Cambiar los niveles de uso compartido de caché para actividades Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)