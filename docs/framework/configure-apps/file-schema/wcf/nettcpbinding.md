---
title: <netTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netTcpBinding Element
ms.assetid: 5c5104a7-8754-4335-8233-46a45322503e
ms.openlocfilehash: c43c141093c8287adb6d5a841a43ac893deefccd
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74139346"
---
# \<netTcpBinding>

Especifica un enlace seguro, confiable y optimizado, adecuado para la comunicación entre equipos. De forma predeterminada, genera una pila de comunicación en tiempo de ejecución con Seguridad de Windows para la seguridad y autenticación de mensajes, TCP para la entrega de mensajes y codificación binaria de mensajes.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netTcpBinding>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<netTcpBinding>
  <binding closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           listenBacklog="Integer"
           maxBufferPoolSize="integer"
           maxBufferSize="Integer"
           maxConnections="Integer"
           maxReceivedMessageSize="Integer"
           name="string"
           openTimeout="TimeSpan"
           portSharingEnabled="Boolean"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           transactionFlow="Boolean"
           transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="None/Transport/Message/Both">
      <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />
      <transport clientCredentialType="None/Windows/Certificate"
                 protectionLevel="None/Sign/EncryptAndSign" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</netTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`closeTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`hostNameComparisonMode`|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|  
|`listenBacklog`|Un entero positivo que especifica el número máximo de canales que esperan ser aceptados en el agente de escucha. Conexiones que sobrepasen este límite se pondrán a la cola hasta que quede disponible un espacio por debajo del límite. El atributo `connectionTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión. El valor predeterminado es 10.|  
|`maxBufferPoolSize`|Entero que especifica el tamaño máximo del grupo de búferes para este enlace. El valor predeterminado es 512 * 1024 bytes. En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes. Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara. Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado. Así se evita la sobrecarga al crear y destruir búferes.|  
|`maxBufferSize`|Un entero positivo que especifica el tamaño máximo, en bytes, del búfer usado para almacenar los mensajes en memoria.<br /><br /> Si el atributo `transferMode` es igual a `Buffered`, este atributo debe ser igual al valor del atributo `maxReceivedMessageSize`.<br /><br /> Si el atributo `transferMode` es igual a `Streamed`, este atributo no puede ser superior al valor del atributo `maxReceivedMessageSize`, y debe tener, al menos, el tamaño de los encabezados.<br /><br /> El valor predeterminado es 65536. Para obtener más información, vea <xref:System.ServiceModel.Configuration.NetNamedPipeBindingElement.MaxBufferSize%2A>.|  
|`maxConnections`|Un entero que especifica el número máximo de conexiones salientes y entrantes que el servicio creará/aceptará. Las conexiones entrantes y salientes se cuentan con respecto a un límite independiente especificado por este atributo.<br /><br /> Las conexiones entrantes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.<br /><br /> Las conexiones salientes que sobrepasen el límite se ponen a la cola hasta que quede disponible un espacio por debajo del límite.<br /><br /> El valor predeterminado es 10.|  
|`maxReceivedMessageSize`|Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace. El remitente de un mensaje que supere este límite recibirá un error SOAP. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536.|  
|`name`|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`portSharingEnabled`|Valor de tipo booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión. Si éste es `false`, cada enlace utiliza su propio puerto exclusivo. Este valor sólo es relevante para los servicios, porque los clientes no se ven afectados.|  
|`receiveTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:10:00.|  
|`sendTimeout`|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|`transactionFlow`|Valor booleano que especifica si el enlace admite las transacciones WS del flujo. De manera predeterminada, es `false`.|  
|`transactionProtocol`|Especifica el protocolo de transacción que se va a usar con este enlace. Los valores válidos son<br /><br /> -OleTransactions<br />-WSAtomicTransactionOctober2004<br /><br /> El valor predeterminado es OleTransactions. Este atributo es del tipo <xref:System.ServiceModel.TransactionProtocol>.|  
|`transferMode`|Un valor <xref:System.ServiceModel.TransferMode> que especifica si los mensajes se almacenan en búfer, se transmiten o si son una solicitud o una respuesta.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-nettcpbinding.md)|Define la configuración de seguridad del enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Comentarios

De forma predeterminada, este enlace genera una pila de comunicación en tiempo de ejecución que usa la seguridad de transporte, TCP para la entrega del mensaje y una codificación de mensajes binaria. Este enlace es una opción proporcionada por el sistema Windows Communication Foundation (WCF) adecuada para la comunicación a través de una intranet.  
  
 La configuración predeterminada de `netTcpBinding` es más rápida que la proporcionada por `wsHttpBinding` , pero está destinada únicamente a la comunicación de WCF. El comportamiento de seguridad es configurable mediante el parámetro opcional `securityMode`. El uso de WS-ReliableMessaging es configurable utilizando el atributo `reliableSessionEnabled` opcional. Pero la mensajería de confianza está apagada de forma predeterminada. Más generalmente, los enlaces proporcionados por el sistema HTTP como `wsHttpBinding` y `basicHttpBinding` se configuran para activar de forma predeterminada las cosas, mientras que el enlace `netTcpBinding` desactiva de forma predeterminada las cosas para que tenga que inscribirse para obtener compatibilidad, por ejemplo, para una de las especificaciones de WS-*. Esto significa que la configuración predeterminada para TCP es más rápida en intercambiar los mensajes entre los puntos de conexión que la configurada de forma predeterminada para los enlaces HTTP.  
  
## <a name="example"></a>Ejemplo

El enlace se especifica en los archivos de configuración para el cliente y servicio. El tipo de enlace se especifica en el atributo de `binding` del elemento `<endpoint>`. Si desea configurar el enlace netTcpBinding y cambiar parte de su configuración, es necesario definir una configuración de enlace. El extremo debe hacer referencia a la configuración de enlace con un atributo `bindingConfiguration`. En el siguiente ejemplo, se define una configuración de enlace.  
  
```xml  
<services>
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    ...
    <endpoint address=""
              binding="netTcpBinding"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />
    ...
  </service>
</services>
<bindings>
  <netTcpBinding>
    <binding closeTimeout="00:01:00"
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"
             maxReceivedMessageSize="65536">
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"
                       enabled="false" />
      <security mode="Transport">
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />
      </security>
    </binding>
  </netTcpBinding>
</bindings>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Configuration.NetTcpBindingElement>
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
