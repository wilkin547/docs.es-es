---
title: '&lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- wsDualHttpBinding Element
ms.assetid: fd8ac4e2-5641-473b-9115-73f14ab1c065
ms.openlocfilehash: 1c03dd0a38264b75b31c9638cf5985a4375aea67
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48782030"
---
# <a name="ltwsdualhttpbindinggt"></a>&lt;wsDualHttpBinding&gt;
Define un enlace seguro, de confianza e interoperable que es apropiado para contratos de servicios dúplex o comunicación a través de los intermediarios de SOAP.  
  
 \<system.ServiceModel>  
\<enlaces >  
\<wsDualHttpBinding>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<wsDualHttpBinding>  
        <binding name="string"  
        closeTimeout="TimeSpan"  
        openTimeout="TimeSpan"   
        receiveTimeout="TimeSpan"  
        sendTimeout="TimeSpan"  
        bypassProxyOnLocal="Boolean"  
        clientBaseAddress="URI"  
        transactionFlow="Boolean"   
        hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"  
        maxBufferPoolSize="integer"  
        maxReceivedMessageSize="Integer"  
        messageEncoding="Text/Mtom"   
        proxyAddress="URI"  
  
textEncoding="Unicode/BigEndianUnicode/UTF8"  
        useDefaultWebProxy="Boolean">  
        <reliableSession ordered="Boolean"  
            inactivityTimeout="TimeSpan" />  
        <security mode="None/Message">  
           <message clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
                negotiateServiceCredential="Boolean"  
                    algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15" />  
                </security>  
       <readerQuotas             maxArrayLength="Integer"            maxBytesPerRead="Integer"            maxDepth="Integer"             maxNameTableCharCount="Integer"                     maxStringContentLength="Integer" />    </binding>  
</wsDualHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|bypassProxyOnLocal|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales. De manera predeterminada, es `false`.|  
|clientBaseAddress|Un URI que establece la dirección base que el cliente escucha para los mensajes de respuesta del servicio. Si se especifica, esta dirección (más una por channelGUID) se utiliza para realizar escuchas. Si no se especifica el valor, la dirección base de clientes se genera de una manera específica del transporte. De manera predeterminada, es `null`.|  
|closeTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|hostnameComparisonMode|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|  
|maxBufferPoolSize|Entero que especifica el tamaño máximo del grupo de búferes para este enlace. El valor predeterminado es 524.288 bytes (512x1024). En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes. Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara. Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado. Así se evita la sobrecarga al crear y destruir búferes.|  
|maxReceivedMessageSize|Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace. El remitente de un mensaje que supere este límite recibirá un error SOAP. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536.|  
|messageEncoding|Define el codificador utilizado para codificar el mensaje. Los valores válidos son los siguientes:<br /><br /> -Text: Utiliza un codificador de mensajes de texto.<br />-Mtom: Usa un codificador Message Transmission organización Mechanism 1.0 (MTOM).<br />-El valor predeterminado es texto.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.|  
|name|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. A partir de [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], no es necesario que los enlaces y los comportamientos tengan nombre. Para obtener más información acerca de la configuración predeterminada y sin especificar enlaces y comportamientos, consulte [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) y [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|proxyAddress|Un URI que especifica la dirección del proxy HTTP. Si `useDefaultWebProxy` es `true`, este valor debe ser `null`. De manera predeterminada, es `null`.|  
|receiveTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|sendTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|textEncoding|Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos son los siguientes:<br /><br /> -BigEndianUnicode: Codificación Unicode BigEndian.<br />-Unicode: codificación de 16 bits.<br />-UTF8: codificación de 8 bits<br /><br /> El valor predeterminado es UTF8. Este atributo es del tipo <xref:System.Text.Encoding>.|  
|transactionFlow|Valor booleano que especifica si el enlace admite las transacciones WS del flujo. De manera predeterminada, es `false`.|  
|useDefaultWebProxy|Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente. La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`. De manera predeterminada, es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<seguridad >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsdualhttpbinding.md)|Define la configuración de seguridad del enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSDualHttpSecurityElement>.|  
|[\<readerQuotas>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[reliableSession](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)|Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<enlaces >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Comentarios  
 `WSDualHttpBinding` proporciona la misma compatibilidad para los protocolos de servicio Web que `WSHttpBinding`, pero para el uso con contratos dúplex. `WSDualHttpBinding` solo admite la seguridad de SOAP y requiere mensajería de confianza. Este enlace requiere que el cliente tenga un URI público que proporciona un extremo de devolución de llamada para el servicio. Lo proporciona el atributo `clientBaseAddress`. Un enlace dual expone la dirección IP del cliente al servicio. El cliente debería utilizar la seguridad para asegurarse de que sólo se conecta a servicios de confianza.  
  
 Este enlace se puede usar para comunicarse con confianza través de uno o más intermediarios SOAP.  
  
 De forma predeterminada, este enlace genera una pila en tiempo de ejecución con WS-ReliableMessaging para la fiabilidad, WS-Security para la seguridad de mensajes y autenticación, HTTP para la entrega de mensajes y una codificación de mensaje texto/XML.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<configuration>  
<system.ServiceModel>  
<bindings>  
<wsDualHttpBinding>  
    <binding   
        closeTimeout="00:00:10"  
        openTimeout="00:00:20"   
        receiveTimeout="00:00:30"  
        sendTimeout="00:00:40"  
        bypassProxyOnLocal="false"   
        clientBaseAddress="http://localhost:8001/client/"  
        transactionFlow="true"   
        hostNameComparisonMode="WeakWildcard"  
        maxReceivedMessageSize="1000"  
        messageEncoding="Mtom"   
        proxyAddress="http://foo/bar"   
        textEncoding="utf-16"  
        useDefaultWebProxy="false">  
        <reliableSession ordered="false"  
            inactivityTimeout="00:02:00" />  
        <security mode="None">  
            <message clientCredentialType="None"  
                negotiateServiceCredential="false"  
                algorithmSuite="Aes128" />  
        </security>  
    </binding>  
</wsDualHttpBinding>  
</bindings>  
</system.ServiceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.WSDualHttpBinding>  
 <xref:System.ServiceModel.Configuration.WSDualHttpBindingElement>  
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)  
 [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Utilización de enlaces para configurar servicios y clientes](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<enlace >](../../../../../docs/framework/misc/binding.md)
