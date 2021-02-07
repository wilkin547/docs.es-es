---
description: 'Más información sobre: <security> de <customBinding>'
title: <security> de <customBinding>
ms.date: 03/30/2017
ms.assetid: 243a5148-bbd1-447f-a8a5-6e7792c0a3f1
ms.openlocfilehash: 0c7a534754f19d46984911ba1dec60d9c517e6b6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683247"
---
# <a name="security-of-custombinding"></a>\<security> de \<customBinding>

Especifica las opciones de seguridad de un enlace personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<security allowSerializedSigningTokenOnReply="Boolean"
          authenticationMode="AuthenticationMode"
          defaultAlgorithmSuite="SecurityAlgorithmSuite"
          includeTimestamp="Boolean"
          requireDerivedKeys="Boolean"
          keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
          messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"
          messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"
          requireDerivedKeys="Boolean"
          requireSecurityContextCancellation="Boolean"
          requireSignatureConfirmation="Boolean"
          securityHeaderLayout="Strict/Lax/LaxTimestampFirst/LaxTimestampLast">
   <issuedTokenParameters />
   <localClientSettings />
   <localServiceSettings />
   <secureConversationBootstrap />
</security>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|allowSerializedSigningTokenOnReply|Opcional. Valor booleano que especifica si un token serializado se puede usar como respuesta. El valor predeterminado es `false`. Cuando use un enlace dual, el valor de la configuración predeterminada es `true` y se ignoran los cambios de configuración realizados.|  
|authenticationMode|Opcional. Especifica el modo de autenticación utilizado entre el iniciador y el respondedor. A continuación encontrará todos los valores.<br /><br /> De manera predeterminada, es `sspiNegotiated`.|  
|defaultAlgorithmSuite|Opcional. Establece el cifrado de mensajes y los algoritmos de encapsulado de claves. La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> A continuación se muestran los valores posibles. El valor predeterminado es `Basic256`.<br /><br /> Se utiliza este atributo al trabajar con una plataforma diferente que opta por un conjunto de algoritmos diferente que el valor predeterminado. Debe tener presentes las ventajas y desventajas de los algoritmos relevantes al efectuar modificaciones en esta configuración. Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|includeTimestamp|Valor booleano que especifica si las marcas de tiempo se incluyen en cada mensaje. De manera predeterminada, es `true`.|  
|keyEntropyMode|Especifica la manera en que se calculan las claves para proteger mensajes. Las claves pueden estar basadas en el material de clave de cliente únicamente, en el servicio de material clave, o en una combinación de ambos. Los valores válidos son<br /><br /> -   `ClientEntropy`: La clave de sesión se basa en los datos clave proporcionados por el cliente.<br />-   `ServerEntropy`: La clave de sesión se basa en los datos clave proporcionados por el servidor.<br />-   `CombinedEntropy`: La clave de sesión se basa en los datos clave proporcionados por el cliente y el servicio.<br /><br /> De manera predeterminada, es `CombinedEntropy`.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|messageProtectionOrder|Establece el orden en el que los algoritmos de seguridad de nivel de mensaje se aplican al mensaje. Los valores válidos incluyen los siguientes:<br /><br /> -   `SignBeforeEncrypt`: Firmar primero y después cifrar.<br />-   `SignBeforeEncryptAndEncryptSignature`: Firme primero, cifre y, a continuación, cifre la firma.<br />-   `EncryptBeforeSign`: Cifre primero y después firme.<br /><br /> El valor predeterminado depende de la versión de WS-Security que se use. `SignBeforeEncryptAndEncryptSignature` cuando se use WS-Security 1,1. `SignBeforeEncrypt` cuando se use WS-Security 1.0.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|messageSecurityVersion|Opcional. Establece la versión de WS-Security que se utiliza. Los valores válidos incluyen los siguientes:<br /><br /> - WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11<br />- WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br />- WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br /><br /> El valor predeterminado es WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11 y se expresa en el XML como simplemente `Default`. Este atributo es del tipo <xref:System.ServiceModel.MessageSecurityVersion>.|  
|requireDerivedKeys|Un valor booleano que especifica si las claves se pueden derivar de las claves de prueba originales. De manera predeterminada, es `true`.|  
|requireSecurityContextCancellation|Opcional. Un valor booleano que especifica si el contexto de seguridad debería ser cancelado y finalizado cuando no sea necesario. De manera predeterminada, es `true`.|  
|requireSignatureConfirmation|Opcional. Un valor booleano que especifica si la confirmación de la firma de Seguridad del WS está habilitada. Cuando se establece en `true`, el respondedor confirma las firmas del mensaje.  Cuando se configura el enlace personalizado para certificados mutuos o para usar los tokens (enlaces de WSS 1.1) emitidos, el valor predeterminado de este atributo es `true`. De lo contrario, el valor predeterminado es `false`.<br /><br /> La confirmación de la firma se utiliza para confirmar que el servicio está respondiendo perfectamente a una solicitud.|  
|securityHeaderLayout|Opcional. Especifica la clasificación de los elementos en el encabezado de seguridad. Los valores válidos son<br /><br /> -   `Strict`: Los elementos se agregan al encabezado de seguridad según el principio general de "declarar antes de usar".<br />-   `Lax`: Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security.<br />-   `LaxWithTimestampFirst`: Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security, salvo que el primer elemento del encabezado de seguridad debe ser un elemento wsse: timestamp.<br />-   `LaxWithTimestampLast`: Los elementos se agregan al encabezado de seguridad en cualquier orden que confirme WSS: SOAP Message Security, salvo que el último elemento en el encabezado de seguridad debe ser un elemento wsse: timestamp.<br /><br /> De manera predeterminada, es `Strict`.<br /><br /> Este elemento es del tipo <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
## <a name="authenticationmode-attribute"></a>Atributo authenticationMode  
  
|Value|Descripción|  
|-----------|-----------------|  
|String|`AnonymousForCertificate`<br /><br /> `AnonymousForSslNegotiated`<br /><br /> `CertificateOverTransport`<br /><br /> `IssuedToken`<br /><br /> `IssuedTokenForCertificate`<br /><br /> `IssuedTokenForSslNegotiated`<br /><br /> `IssuedTokenOverTransport`<br /><br /> `Kerberos`<br /><br /> `KerberosOverTransport`<br /><br /> `MutualCertificate`<br /><br /> `MutualCertificateDuplex`<br /><br /> `MutualSslNegotiated`<br /><br /> `SecureConversation`<br /><br /> `SspiNegotiated`<br /><br /> `UserNameForCertificate`<br /><br /> `UserNameForSslNegotiated`<br /><br /> `UserNameOverTransport`<br /><br /> `SspiNegotiatedOverTransport`|  
  
## <a name="defaultalgorithm-attribute"></a>Atributo defaultAlgorithm  
  
|Value|Descripción|  
|-----------|-----------------|  
|Basic128|Utilice el cifrado Aes128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic192|Utilice el cifrado Aes192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic256|Utilice el cifrado Aes256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el cifrado de claves.|  
|Basic256Rsa15|Utilice Aes256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Rsa15|Utilice Aes192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDes|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic128Rsa15|Utilice Aes128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesRsa15|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic128Sha256|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic192Sha256|Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic256Sha256|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|TripleDesSha256|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic128Sha256Rsa15|Utilice Aes128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Sha256Rsa15|Utilice Aes192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic256Sha256Rsa15|Utilice Aes256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesSha256Rsa15|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](issuedtokenparameters.md)|Especifica un token emitido actual. Este elemento es del tipo <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<localClientSettings>](localclientsettings-element.md)|Especifica la configuración de seguridad de un cliente local para este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<localServiceSettings>](localservicesettings-element.md)|Especifica la configuración de seguridad de un servicio local para este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
|[\<secureConversationBootstrap>](secureconversationbootstrap.md)|Especifica los valores predeterminados usados para iniciar un servicio de conversación seguro.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Observaciones  

 Para obtener más información sobre el uso de este elemento, vea [modos de autenticación de SecurityBindingElement](../../../wcf/feature-details/securitybindingelement-authentication-modes.md) y [Cómo: crear un enlace personalizado mediante SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
## <a name="example"></a>Ejemplo  

 El ejemplo siguiente muestra cómo configurar la seguridad mediante un enlace personalizado. Muestra cómo utilizar un enlace personalizado para habilitar la seguridad de nivel de mensaje junto con un transporte seguro. Esto es útil cuando se exige un transporte seguro que transmita los mensajes entre el cliente y servicio y simultáneamente los mensajes deben ser seguros en el nivel de mensaje. Los enlaces proporcionados por el sistema no admiten esta configuración.  
  
 La configuración de servicio define un enlace personalizado que admite la protección de la comunicación del TCP utilizando TLS/protocolo SSL y modo de seguridad de Windows. El enlace personalizado utiliza un certificado de servicio para autenticar el servicio en el nivel de transporte y proteger los mensajes durante la transmisión entre el cliente y servicio. Esto se logra mediante el [\<sslStreamSecurity>](sslstreamsecurity.md) elemento de enlace. El certificado del servicio se configura utilizando un comportamiento del servicio.  
  
 Además, el enlace personalizado utiliza seguridad de mensajes con tipo de credencial de Windows; éste es el tipo de credencial predeterminado. Esto se logra mediante el elemento de enlace de [seguridad](security-of-custombinding.md) . El cliente y el servicio se autentican utilizando la seguridad del nivel de mensaje si el mecanismo de autenticación Kerberos está disponible. Si el mecanismo de autenticación Kerberos no está disponible, se utiliza la autenticación NTLM. NTLM autentica el cliente al servicio pero no autentica el servicio al cliente. El elemento de enlace de [seguridad](security-of-custombinding.md) se configura para utilizar `SecureConversation` authenticationType, lo que da como resultado la creación de una sesión de seguridad tanto en el cliente como en el servicio. Esto se exige para que funcione el contrato del dúplex del servicio. Para obtener más información sobre cómo ejecutar este ejemplo, vea [seguridad de enlace personalizado](../../../wcf/samples/custom-binding-security.md).  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- use following base address -->
            <add baseAddress="net.tcp://localhost:8000/ServiceModelSamples/Service"/>
          </baseAddresses>
        </host>
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
        <!-- the mex endpoint is exposed at net.tcp://localhost:8000/ServiceModelSamples/service/mex -->
        <endpoint address="mex"
                  binding="mexTcpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <bindings>
      <!-- configure a custom binding -->
      <customBinding>
        <binding name="Binding1">
          <security authenticationMode="SecureConversation"
                    requireSecurityContextCancellation="true">
          </security>
          <textMessageEncoding messageVersion="Soap12WSAddressing10"
                               writeEncoding="utf-8" />
          <sslStreamSecurity requireClientCertificate="false" />
          <tcpTransport />
        </binding>
      </customBinding>
    </bindings>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata />
          <serviceDebug includeExceptionDetailInFaults="False" />
          <serviceCredentials>
            <serviceCertificate findValue="localhost"
                                storeLocation="LocalMachine"
                                storeName="My"
                                x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.SecurityElement>
- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
- [Procedimiento para crear un enlace personalizado mediante SecurityBindingElement](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Seguridad de enlace personalizado](../../../wcf/samples/custom-binding-security.md)
