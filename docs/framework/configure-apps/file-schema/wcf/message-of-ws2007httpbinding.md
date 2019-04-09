---
title: <message> de <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
ms.openlocfilehash: bf0ed2de73505d5634d6c7d26881f9800a0bf1f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166743"
---
# <a name="message-of-ws2007httpbinding"></a>\<mensaje > de \<ws2007HttpBinding >
Define la configuración de seguridad de nivel de mensaje de la [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) elemento.  
  
 \<system.ServiceModel>  
\<bindings>  
\<ws2007HttpBinding>  
\<binding>  
\<security>  
\<message>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<ws2007HttpBinding>
  <binding>
    <security>
      <message clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"
               establishSecurityContext="Boolean"
               negotiateServiceCredential="Boolean"
               algorithmSuite="Enumeration. See algorithmSuite Attribute below."
               defaultProtectionLevel="None/Sign/EncryptionAndSign" />
    </security>
  </binding>
</ws2007HttpBinding>
```  
  
## <a name="type"></a>Tipo  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`algorithmSuite`|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves. La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave. Estos algoritmos se asignan a los indicados en la especificación Lenguaje de directiva de seguridad (WS-SecurityPolicy).<br /><br /> El valor predeterminado es Basic256.|  
|`clientCredentialType`|Opcional. Especifica que el tipo de credencial que se va a usar al realizar la autenticación del cliente mediante el modo de seguridad `Message` o `TransportWithMessageCredentials`. Vea los valores de enumeración en la siguiente tabla. El valor predeterminado es Windows.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|  
|`establishSecurityContext`|Un valor que determina si el canal de seguridad establece una sesión segura. Una sesión segura establece un token de contexto de seguridad (SCT) antes de intercambiar los mensajes de la aplicación. Cuando se establece el SCT, el canal de seguridad ofrece una interfaz <xref:System.ServiceModel.Channels.ISession> a los canales superiores. Para obtener más información sobre el uso de las sesiones seguras, vea [Cómo: Crear una sesión segura](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> El valor predeterminado es `true`.|  
|`negotiateServiceCredential`|Opcional. Un valor que especifica si la credencial de servicio se proporciona en el cliente fuera de banda o se obtiene del servicio al cliente a través de un proceso de negociación. Este tipo de negociación es un precursor del intercambio de mensajes usual.<br /><br /> Si el `clientCredentialType` atributo es igual a ninguno, Username o Certificate, establecer este atributo en `false` implica que el certificado de servicio está disponible en el cliente fuera de banda y que el cliente debe especificar el certificado de servicio (mediante el [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) en el [ \<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) comportamiento del servicio. Este modo es interoperable con pilas SOAP que implementan WS-Trust y WS-SecureConversation.<br /><br /> Si el atributo `ClientCredentialType` está establecido en `Windows`, establecer este atributo en `false` especifica la autenticación basada en Kerberos. Esto significa que el cliente y el servicio deben formar parte del mismo dominio Kerberos. Este modo es interoperable con pilas SOAP que implementan el perfil de token de Kerberos (tal y como se define en OASIS WSS TC), así como WS-Trust y WS-SecureConversation.<br /><br /> Cuando este atributo es `true`, produce una negociación .NET SOAP que tuneliza el intercambio de <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> mediante mensajes SOAP.<br /><br /> De manera predeterminada, es `true`.|  
  
## <a name="algorithmsuite-attribute"></a>atributo algorithmSuite  
  
|Valor|Descripción|  
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
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`None`|Esto permite al servicio interactuar con clientes anónimos. En el servicio, esto indica que el servicio no requiere ninguna credencial del cliente. En el cliente, esto indica que el cliente no proporciona ninguna credencial del cliente.|  
|`Certificate`|Permite al servicio exigir la autenticación del cliente mediante un certificado. Si se usa el modo de seguridad de `message` y el atributo `negotiateServiceCredential` está establecido en `false`, se debe proporcionar al cliente el certificado de servicio.|  
|`IssuedToken`|Especifica un token personalizado, normalmente emitido por un servicio de token de seguridad (STS).|  
|`UserName`|Permite al servicio exigir la autenticación del cliente mediante una credencial `UserName`. WCF no admite enviar un resumen de contraseña ni derivar claves mediante contraseña y utilizando tales claves para seguridad de mensajes. Por lo tanto, WCF impone que el transporte sea seguro al usar `UserName` credenciales. Este modo de credencial produce o bien un intercambio interoperable o bien una negociación no interoperable basada en el atributo `negotiateServiceCredential`.|  
|`Windows`|Permite a los intercambios de SOAP estar bajo el contexto autenticado de una credencial de `Windows`. Si el atributo `negotiateServiceCredential` está establecido en `true`, esto realiza una negociación de SSPI o Kerberos (una norma interoperable).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguna  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Define la configuración de seguridad para un [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md).|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>
- [Protección de servicios y clientes](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../../../docs/framework/wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
