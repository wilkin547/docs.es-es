---
title: <wsFederationHttpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- wsFederationBinding element
ms.assetid: 9c3312b4-2137-4e71-bf3f-de1cf8e9be79
ms.openlocfilehash: 0a77c791d55c6009cf59d5a4b15f3b2a63b7ccf9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74140474"
---
# \<wsFederationHttpBinding>

Define un enlace que admite WS-Federation.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<wsFederationHttpBinding>**  

## <a name="syntax"></a>Sintaxis

```xml
<wsFederationHttpBinding>
  <binding bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
           maxBufferPoolSize="integer"
           maxReceivedMessageSize="integer"
           messageEncoding="Text/Mtom"
           name="string"
           openTimeout="TimeSpan"
           privacyNoticeAt="Uri"
           privacyNoticeVersion="Integer"
           proxyAddress="Uri"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/ Utf8TextEncoding"
           transactionFlow="Boolean"
           useDefaultWebProxy="Boolean">
    <security mode="None/Message/TransportWithMessageCredential">
      <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
               issuedTokenType="string"
               issuedKeyType="SymmetricKey/PublicKey"
               negotiateServiceCredential="Boolean">
        <claimTypeRequirements>
          <add claimType="URI"
               isOptional="Boolean" />
        </claimTypeRequirements>
        <issuer address="Uri" >
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  X509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuer>
        <issuerMetadata address="String">
          <headers>
            <add name="String"
                 namespace="String" />
          </headers>
          <identity>
            <certificate encodedValue="String" />
            <certificateReference findValue="String"
                                  isChainIncluded="Boolean"
                                  storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
                                  storeLocation="LocalMachine/CurrentUser"
                                  x509FindType="System.Security.Cryptography.X509certificates.X509findtype" />
            <dns value="String" />
            <rsa value="String" />
            <servicePrincipalName value="String" />
            <usePrincipalName value="String" />
          </identity>
        </issuerMetadata>
        <tokenRequestParameters>
          <xmlElement>
          </xmlElement>
        </tokenRequestParameters>
      </message>
    </security>
    <reliableSession ordered="Boolean"
                     inactivityTimeout="TimeSpan"
                     enabled="Boolean" />
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</wsFederationBinding>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|bypassProxyOnLocal|Valor de tipo booleano que indica si se omitirá el servidor proxy para las direcciones locales. De manera predeterminada, es `false`.|
|closeTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|
|hostnameComparisonMode|Especifica el modo de comparación de nombres de host HTTP usado para analizar los URI. Este atributo es del tipo <xref:System.ServiceModel.HostNameComparisonMode>, que indica si se va a utilizar el nombre del host para llegar al servicio cuando coincida en el URI. El valor predeterminado es <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, que omite el nombre del host en la coincidencia.|
|maxBufferPoolSize|Entero que especifica el tamaño máximo del grupo de búferes para este enlace. El valor predeterminado es 524.288 bytes (512x1024). En muchas partes de Windows Communication Foundation (WCF) se utilizan búferes. Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara. Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado. Así se evita la sobrecarga al crear y destruir búferes.|
|maxReceivedMessageSize|Entero positivo que especifica el tamaño máximo del mensaje, en bytes, incluidos los encabezados, que se puede recibir en un canal configurado con este enlace. El remitente de un mensaje que supere este límite recibirá un error SOAP. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536.|
|messageEncoding|Define el codificador utilizado para codificar el mensaje. Los valores válidos incluyen los siguientes:<br /><br /> -Text: usar un codificador de mensajes de texto.<br />-MTOM: usar un codificador del mecanismo de la organización de transmisión de mensajes 1,0 (MTOM).<br /><br /> El valor predeterminado es Text.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.WSMessageEncoding>.|
|name|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|
|openTimeout|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|
|privacyNoticeAt|Una cadena que especifica un URI en el que el aviso de privacidad se encuentra.|
|privacyNoticeVersion|Un entero que especifica la versión del aviso de privacidad actual.|
|proxyAddress|Un URI que especifica la dirección del proxy HTTP. Si `useDefaultWebProxy` es `true`, este valor debe ser `null`. De manera predeterminada, es `null`.|
|receiveTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:10:00.|
|sendTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|
|textEncoding|Establece el codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace. Los valores válidos incluyen los siguientes:<br /><br /> -BigEndianUnicode: codificación Unicode BigEndian.<br />-Unicode: codificación de 16 bits.<br />-UTF8: codificación de 8 bits<br /><br /> El valor predeterminado es UTF8. Este atributo es del tipo <xref:System.Text.Encoding>.|
|transactionFlow|Valor booleano que especifica si el enlace admite las transacciones WS del flujo. De manera predeterminada, es `false`.|
|useDefaultWebProxy|Valor de tipo booleano que indica si se utiliza el proxy HTTP del sistema configurado automáticamente. La dirección de proxy debe ser `null` (es decir, sin establecer) si este atributo es `true`. De manera predeterminada, es `true`.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<security>](security-of-wsfederationhttpbinding.md)|Define la configuración de seguridad del mensaje. Este elemento es del tipo <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>.|
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Define las restricciones en la complejidad de los mensajes SOAP que pueden ser procesados por los puntos de conexión configurados con este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|
|[\<reliableSession>](https://docs.microsoft.com/previous-versions/ms731375(v=vs.90))|Especifica si se establecen sesiones confiables entre los puntos de conexión del canal.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<bindings>](bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|

## <a name="remarks"></a>Comentarios

La federación es la capacidad de compartir identidades en varios sistemas para la autenticación y autorización. Estas identidades pueden hacer referencia a usuarios o a equipos. El HTTP federado admite la seguridad de SOAP así como la seguridad de modo mixto, pero no permite utilizar únicamente la seguridad de transporte. Este enlace proporciona compatibilidad con Windows Communication Foundation (WCF) para el protocolo WS-Federation. Los servicios configurados con este enlace deben utilizar el transporte de HTTP.

Los enlaces están compuestos de una pila de elementos de enlace. La pila de elementos de enlace en

`wsFederationHttpBinding`es la misma que la que contiene `wsHttpBinding`

Cuando [\<security>](security-of-wsfederationhttpbinding.md) se establece en el valor predeterminado de <xref:System.ServiceModel.WSFederationHttpSecurityMode.Message> .

`wsFederationHttpBinding`Controla los detalles de la configuración de seguridad del mensaje en [\<message>](message-element-of-wsfederationhttpbinding.md) . Tenga en cuenta que el [\<security>](security-of-wsfederationhttpbinding.md) elemento proporciona acceso solo cuando la seguridad que usa el enlace no se puede cambiar una vez creado el enlace.

`wsFederationHttpBinding`También proporciona un atributo privacyNoticeAt para establecer y recuperar el URI en el que se encuentra el aviso de privacidad.

Mantener la directiva protegida es especialmente importante en escenarios de federación. Se recomienda utilizar algún formulario de seguridad, como HTTPS, para proteger la directiva de los usuarios malintencionados.

En los escenarios de federación que utilizan este enlace, la directiva del servicio tiene potencialmente información importante como la clave para utilizar para cifrar el token emitido (SAML), el tipo de demandas para introducir el token, etc. Si esta directiva se manipula, un atacante podría detectar la clave del token emitido que conduce a una modificación posterior, divulgación de información y otros comportamientos malintencionados. Para ayudar a evitar esto, la directiva se debe obtener firmemente (utilizando HTTPS, por ejemplo) del servicio.

Para obtener más información sobre este enlace, vea [Cómo: crear un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md).

## <a name="example"></a>Ejemplo

```xml
<configuration>
  <system.ServiceModel>
    <bindings>
      <wsFederationHttpBinding>
        <binding bypassProxyOnLocal="false"
                 transactionFlow="false"
                 hostNameComparisonMode="WeakWildcard"
                 maxReceivedMessageSize="1000"
                 messageEncoding="Mtom"
                 proxyAddress="http://foo/bar"
                 textEncoding="Utf16TextEncoding"
                 useDefaultWebProxy="false">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="None">
            <message negotiateServiceCredential="false"
                     algorithmSuite="Aes128"
                     issuedTokenType="saml"
                     issuedKeyType="PublicKey">
              <issuer address="http://localhost/Sts" />
            </message>
          </security>
        </binding>
      </wsFederationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```

## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.WSFederationHttpBinding>
- <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement>
- [Procedimiento para crear un WSFederationHttpBinding](../../../wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
