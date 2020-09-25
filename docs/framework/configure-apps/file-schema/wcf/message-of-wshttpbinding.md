---
title: <message> de <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 621abbde-590b-454d-90ac-68dc3c69c720
ms.openlocfilehash: 7bd4caa31dcdcd2a4b104b9d4d5615a2ff800db4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204831"
---
# <a name="message-of-wshttpbinding"></a>\<message> de \<wsHttpBinding>

Define la configuración para la seguridad de nivel de mensaje de [\<wsHttpBinding>](wshttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
         establishSecurityContext="Boolean"
         negotiateServiceCredential="Boolean" />
```  
  
## <a name="type"></a>Tipo  

 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|algorithmSuite|Establece el cifrado de mensajes y los algoritmos de encapsulado de claves. La clase <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> determina los algoritmos y los tamaños de clave. Estos algoritmos se asignan a los que se indican en la especificación Security Policy Language (WS-SecurityPolicy).<br /><br /> El valor predeterminado es `Basic256`.|  
|clientCredentialType|Opcional. Especifica que el tipo de credenciales que se van a usar al realizar la autenticación del cliente mediante el modo de seguridad es o `Message` o `TransportWithMessageCredentials`. Vea los valores de enumeración valora a continuación. El valor predeterminado es `Windows`.<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.MessageCredentialType>.|  
|establishSecurityContext|Un valor booleano que determina si el canal de seguridad establece una sesión segura. Una sesión segura establece un token de contexto de seguridad (SCT) antes de intercambiar los mensajes de la aplicación. Cuando se establece el SCT, el canal de seguridad ofrece una interfaz <xref:System.ServiceModel.Channels.ISession> a los canales superiores. Para obtener más información sobre el uso de sesiones seguras, consulte [Cómo: crear una sesión segura](../../../wcf/feature-details/how-to-create-a-secure-session.md).<br /><br /> El valor predeterminado es `true`.|  
|negotiateServiceCredential|Opcional. Un valor booleano que especifica si la credencial de servicio se proporciona en el cliente fuera de banda o se obtiene del servicio al cliente a través de un proceso de negociación. Este tipo de negociación es un precursor del intercambio de mensajes usual.<br /><br /> Si el `clientCredentialType` atributo es igual a ninguno, nombre de usuario o certificado, establecer este atributo en `false` implica que el certificado de servicio está disponible en el cliente fuera de banda y que el cliente necesita especificar el certificado de servicio (mediante [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) ) en el [\<serviceCredentials>](servicecredentials.md) comportamiento del servicio. Este modo es interoperable con pilas SOAP que implementan WS-Trust y WS-SecureConversation.<br /><br /> Si el atributo `ClientCredentialType` está establecido en `Windows`, establecer este atributo en `false` especifica la autenticación basada en Kerberos. Esto significa que el cliente y el servicio deben formar parte del mismo dominio Kerberos. Este modo es interoperable con pilas SOAP que implementan el perfil de token de Kerberos (tal y como se define en OASIS WSS TC), así como WS-Trust y WS-SecureConversation.<br /><br /> Cuando este atributo es `true`, produce una negociación .NET SOAP que tuneliza el intercambio de SPNego mediante mensajes SOAP.<br /><br /> El valor predeterminado es `true`.|  
  
## <a name="algorithmsuite-attribute"></a>atributo algorithmSuite  
  
|Value|Descripción|  
|-----------|-----------------|  
|Basic128|Utilice el cifrado Basic128, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic192|Utilice el cifrado Basic192, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic256|Utilice el cifrado Basic256, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic256Rsa15|Utilice Basic256 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Rsa15|Utilice Basic192 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDes|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic128Rsa15|Utilice Basic128 para el cifrado de mensajes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesRsa15|Utilice el cifrado TripleDes, Sha1 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic128Sha256|Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic192Sha256|Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic256Sha256|Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|TripleDesSha256|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa-oaep-mgf1p para el encapsulado de claves.|  
|Basic128Sha256Rsa15|Utilice Basic128 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic192Sha256Rsa15|Utilice Basic192 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|Basic256Sha256Rsa15|Utilice Basic256 para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
|TripleDesSha256Rsa15|Utilice TripleDes para el cifrado de mensajes, Sha256 para la síntesis del mensaje y Rsa15 para el encapsulado de claves.|  
  
## <a name="clientcredentialtype-attribute"></a>Atributo clientCredentialType  
  
|Value|Descripción|  
|-----------|-----------------|  
|None|Esto permite al servicio interactuar con clientes anónimos. En el lado del servicio, esto indica que el servicio no requiere ninguna credencial del cliente. En el cliente, esto indica que el cliente no proporciona ninguna credencial del cliente.|  
|Certificado|Permite al servicio exigir la autenticación del cliente mediante un certificado. Si se utiliza el modo de seguridad del mensaje y el atributo `negotiateServiceCredential` está establecido como `false`, se necesita proporcionar al cliente el certificado de servicio.|  
|IssuedToken|Especifica un token personalizado, normalmente emitido por un servicio de token de seguridad.|  
|UserName|Permite que el servicio requiera que el cliente se autentique con una credencial UserName. WCF no admite el envío de una síntesis de contraseña o la derivación de claves mediante contraseña y el uso de dichas claves para la seguridad de los mensajes. Como tal, WCF exige que el transporte sea seguro al utilizar las credenciales de nombre de usuario. Este modo de credencial produce o bien un intercambio interoperable o bien una negociación no interoperable basada en el atributo `negotiateServiceCredential`.|  
|Windows|Permite a los intercambios de SOAP estar bajo el contexto autenticado de una credencial de Windows. Si el atributo `negotiateServiceCredential` está establecido en `true`, esto realiza una Negociación de la SSPI o Kerberos (una norma interoperable).|  
  
### <a name="child-elements"></a>Elementos secundarios  

 None  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-wshttpbinding.md)|Define la configuración de seguridad para un [\<wsHttpBinding>](wshttpbinding.md) .|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>
- [Protección de servicios y clientes](../../../wcf/feature-details/securing-services-and-clients.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
