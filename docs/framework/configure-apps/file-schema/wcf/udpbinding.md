---
title: '&lt;udpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fa291901-8340-45c6-9c44-5d9281c70bc3
ms.openlocfilehash: 1d9535f60bca101e53b678da25915ac9afb41aab
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756220"
---
# <a name="ltudpbindinggt"></a>&lt;udpBinding&gt;
Un elemento de configuración usado para configurar el enlace <xref:System.ServiceModel.UdpBinding>.  
  
 \<system.ServiceModel>  
\<enlaces >  
\<udpBinding >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<udpBinding>  
   <binding   
       closeTimeout="TimeSpan"   
       duplicateMessageHistoryLength="Integer"  
       maxBufferPoolSize="Integer"  
       maxBufferSize="Integer"       maxPendingMessagesTotalSize="Integer"  
       maxReceivedMessageSize="Integer"       maxRetransmitCount="Integer"  
       multicastInterfaceId="Integer"  
              name="string"   
       openTimeout="TimeSpan"   
       receiveTimeout="TimeSpan"  
       sendTimeout="TimeSpan"  
       textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"  
       timeToLive="TimeSpan">  
       <readerQuotas   
            maxArrayLength="Integer"  
            maxBytesPerRead="Integer"  
            maxDepth="Integer"             maxNameTableCharCount="Integer"                maxStringContentLength="Integer" />  
   </binding>  
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`closeTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`duplicateMessageHistoryLength`|Un valor entero que especifica la longitud duplicada del historial de mensajes.|  
|`maxBufferPoolSize`|Un valor entero que especifica la cantidad de memoria máxima que se asigna para el uso realizado por el administrador de los búferes que reciben los mensajes del canal. El valor predeterminado es 524288 (0x80000) bytes.|  
|`maxBufferSize`|Un valor entero que especifica el tamaño máximo, en bytes, de un búfer que almacena los mensajes mientras se procesan para un extremo configurado con este enlace. El valor predeterminado es 65.536 bytes.|  
|`maxPendingMessagesTotalSize`|Valor entero que especifica el número máximo de mensajes que se han recibido pero que todavía no se han quitado de la cola de entrada para una instancia del canal individual.|  
|`maxReceivedMessageSize`|Un entero positivo que define el tamaño máximo del mensaje, en bytes, incluidos los encabezados, para un mensaje que se puede recibir en un canal configurado con este enlace. El remitente recibe un error SOAP cuando el mensaje es demasiado grande para el receptor. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65.536 bytes.|  
|`maxRetransmitCount`|Valor entero de que especifica el número máximo de mensajes de retransmisión.|  
|`multicastInterfaceId`|Valor entero que especifica el identificador de la interfaz de multidifusión.|  
|`name`|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. Cada enlace tiene los atributos `name` y `namespace` que, juntos, lo identifican de forma exclusiva en los metadatos del servicio. Además, este nombre es único entre los enlaces del mismo tipo. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información acerca de la configuración predeterminada y enlaces anónimos y los comportamientos, consulte [configuración simplificada](../../../../../docs/framework/wcf/simplified-configuration.md) y [configuración simplificada para los servicios WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`receiveTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:10:00.|  
|`sendTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`textEncoding`|Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos son los siguientes:<br /><br /> -BigEndianUnicode: Codificación Unicode BigEndian.<br />-Unicode: codificación de 16 bits.<br />-UTF8: codificación de 8 bits<br /><br /> El valor predeterminado es UTF8. Este atributo es del tipo <xref:System.Text.Encoding>.|  
|`timeToLive`|Valor timespan que especifica el período de vida para el enlace.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<readerQuotas>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enlaces >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Comentarios  
 El UdpBinding permite que los servicios de WCF se comuniquen sobre el transporte UDP. Permite intercambios de mensajes "desencadenar y omitir" donde un cliente envía un mensaje a un servicio y no espera ninguna respuesta.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar <xref:System.ServiceModel.UdpBinding> con el elemento <`udpBinding`>.  
  
```xml  
<udpBinding>  
        <binding  closeTimeout="00:10:00"  
                   duplicateMessageHistoryLength="100"  
                   maxBufferPoolSize="100"  
                   maxPendingMessagesTotalSize="100000"  
                   maxReceivedMessageSize="65536"  
                    maxRetransmitCount="10"  
                   multicastInterfaceId="00000"  
                   name="myUdpBinding"  
                   openTimeout="00:10:00"  
                   receiveTimeout="00:10:00"  
                   sendTimeout="00:10:00"  
                   textEncoding="utf-8"  
                   timeToLive="00:10:00"  
          <readerQuotas/>   
        </binding>  
      </udpBinding>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar los clientes y servicios de Windows Communication Foundation](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<enlace >](../../../../../docs/framework/misc/binding.md)
