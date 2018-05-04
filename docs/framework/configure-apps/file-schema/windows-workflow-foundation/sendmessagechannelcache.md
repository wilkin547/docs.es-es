---
title: '&lt;sendMessageChannelCache&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 241e428e-5030-4b13-8a0a-69f05288d3d9
ms.openlocfilehash: 9fb68fb8ef4b1fa74a36005c80dc568e227c6473
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsendmessagechannelcachegt"></a>&lt;sendMessageChannelCache&gt;
Un comportamiento de servicio que permite la personalización de la memoria caché de uso compartido de niveles, la configuración de la memoria de caché del generador de canales y la configuración de la memoria caché de canales para los flujos de trabajo que envían mensajes a extremos de servicio mediante actividades de mensajería de envío.  
  
\<system.ServiceModel>  
\<comportamientos >  
\<serviceBehaviors >  
\<comportamiento >  
\<sendMessageChannelCache >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan"
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|allowUnsafeCaching|Un valor booleano que indica si debe activarse el almacenamiento en la memoria caché. Si su servicio de flujo de trabajo tiene enlaces personalizados o los comportamientos personalizados, el almacenamiento en la memoria caché podría no ser seguro y, por consiguiente, está deshabilitado de forma predeterminada. Sin embargo, si desea activar el almacenamiento en caché en establezca esta propiedad en **true**.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<channelSettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/channelsettings.md)|Especifica los valores de la memoria caché del canal.|  
|[\<factorySettings >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/factorysettings.md)|Especifica los valores de la memoria caché del generador de canales.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<comportamiento > de \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Especifica un elemento de comportamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Este comportamiento del servicio está orientado para los flujos de trabajo que envían mensajes a los extremos de servicio. Estos flujos de trabajo son normalmente flujos de trabajo del cliente pero podrían ser también servicios de flujo de trabajo que se hospedan en <xref:System.ServiceModel.WorkflowServiceHost>.  
  
 De manera predeterminada, en un flujo de trabajo hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché usada por las actividades de mensajería de <xref:System.ServiceModel.Activities.Send> se comparte en todas las instancias de flujo de trabajo en <xref:System.ServiceModel.WorkflowServiceHost> (el almacenamiento en caché de nivel de host). Para un flujo de trabajo del cliente que no esté hospedado por <xref:System.ServiceModel.WorkflowServiceHost>, la memoria caché está solo disponible para la instancia de flujo de trabajo (almacenamiento en caché en el nivel de instancia). El almacenamiento en la memoria caché está deshabilitado de forma predeterminada para cualquier actividad de envío del flujo de trabajo que tenga definidos puntos de conexión en su configuración.  
  
 Para obtener más información sobre cómo cambiar la memoria caché predeterminada compartir niveles y configuración de la caché para el generador de canales y la memoria caché de canales, vea [cambiar los niveles de uso compartido de caché para las actividades de envío](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).  
  
## <a name="example"></a>Ejemplo  
 En un servicio de flujo de trabajo hospedado, puede especificar la configuración de la memoria caché del generador y del canal en el archivo de configuración de la aplicación. Para ello, agregue un comportamiento de servicio que contenga los valores de memoria caché para el generador y memoria caché del canal, y agregue este comportamiento de servicio a su servicio. En el ejemplo siguiente se muestra el contenido de un archivo de configuración que contiene el **MyChannelCacheBehavior** comportamiento de servicio con la configuración de caché de memoria caché y canal de generador personalizado. Este comportamiento de servicio se agrega al servicio a través de la **behaviorConfiguarion** atributo.  
  
```xml  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 [Cambio de los niveles de uso compartido de caché para actividades Send](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
