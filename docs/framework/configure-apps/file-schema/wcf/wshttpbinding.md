---
title: <wsHttpBinding>
description: Define un enlace HTTP seguro, confiable e interoperable adecuado para contratos de servicio no dúplex, que implementa la mensajería WS-Reliable Messaging y WS-Security.
ms.date: 03/30/2017
helpviewer_keywords:
- wsHttpBinding Element
ms.assetid: 0eee8ced-ad68-427d-b95a-97260e98deed
ms.openlocfilehash: d603f699145622cb1b70ecf99ea542572e841eac
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243989"
---
# \<wsHttpBinding>
Define un enlace seguro, de confianza e interoperable, adecuado para contratos de servicio no dúplex. El enlace implementa las características siguientes: WS-Reliable Messaging para confiabilidad y WS-Security para la seguridad del mensaje y autenticación. El transporte es HTTP y la codificación del mensaje es codificación de texto/XML.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsHttpBinding>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<wsHttpBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <security mode="Message/None/Transport/TransportWithCredential">
      <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                 proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                 realm="string" />
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|allowCookies|Valor de tipo booleano que indica si el cliente acepta las cookies y las propaga en solicitudes futuras. El valor predeterminado es false.<br /><br /> Puede utilizar esta propiedad al interactuar con los servicios Web ASMX que utilizan cookies. De esta manera, puede estar seguro de que las cookies devueltas del servidor se copian automáticamente en todas las solicitudes de cliente futuras para ese servicio.|  
|bypassProxyOnLocal|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales. De manera predeterminada, es `false`.|  
|closeTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|hostnameComparisonMode|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|  
|maxBufferPoolSize|Entero que especifica el tamaño máximo del grupo de búferes para este enlace. El valor predeterminado es 524.288 bytes (512x1024). En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes. Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara. Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado. Así se evita la sobrecarga al crear y destruir búferes.|  
|maxReceivedMessageSize|Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace. El remitente de un mensaje que supere este límite recibirá un error SOAP. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536.|  
|messageEncoding|Define el codificador utilizado para codificar el mensaje. Los valores válidos incluyen los siguientes:<br /><br /> -Text: usar un codificador de mensajes de texto.<br />-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).<br />-El valor predeterminado es texto.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.|  
|name|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|proxyAddress|Un URI que especifica la dirección del proxy HTTP. Si `useSystemWebProxy` es `true`, este valor debe ser `null`. De manera predeterminada, es `null`.|  
|receiveTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|sendTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|textEncoding|Especifica el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos incluyen los siguientes:<br /><br /> -UnicodeFffeTextEncoding: codificación Unicode BigEndian.<br />-Utf16TextEncoding: codificación de 16 bits.<br />-Utf8TextEncoding: codificación de 8 bits.<br /><br /> El valor predeterminado es Utf8TextEncoding.<br /><br /> Este atributo es del tipo <xref:System.Text.Encoding>.|  
|transactionFlow|Valor booleano que especifica si el enlace admite las transacciones WS del flujo. De manera predeterminada, es `false`.|  
|useDefaultWebProxy|Valor de tipo booleano que especifica si se utiliza el proxy HTTP del sistema configurado automáticamente. De manera predeterminada, es `true`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|Define la configuración de seguridad del enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Comentarios  
 La clase `WSHttpBinding` es similar a la clase `BasicHttpBinding` pero proporciona más características de servicios Web. Utiliza el transporte HTTP y proporciona seguridad para mensajes, como BasicHttpBinding, pero también proporciona transacciones, mensajería confiable y WS-Addressing, habilitada de forma predeterminada o disponible mediante un valor de control único.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsHttpBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="utf-16"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="Transport">
            <transport clientCredentialType="Digest"
                       proxyCredentialType="None"
                       realm="someRealm" />
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     defaultProtectionLevel="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement>
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
