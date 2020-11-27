---
title: Modos de autenticación de SecurityBindingElement
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
ms.openlocfilehash: bf1b8103714c174fc2746bc864a7d7e0e5ea5ff1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253991"
---
# <a name="securitybindingelement-authentication-modes"></a>Modos de autenticación de SecurityBindingElement

Windows Communication Foundation (WCF) proporciona varios modos en los que los clientes y servicios se autentican entre sí. Puede crear elementos de enlace de seguridad para estos modos de autenticación utilizando los métodos estáticos en la clase <xref:System.ServiceModel.Channels.SecurityBindingElement> o a través de la configuración. Este tema describe brevemente los 18 modos de autenticación.  
  
 Para obtener un ejemplo del uso del elemento para uno de los modos de autenticación, consulte [Cómo: crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="basic-configuration-programming"></a>Programación de configuración básica  

 El procedimiento siguiente describe cómo establecer el modo de autenticación en un archivo de configuración.  
  
#### <a name="to-set-the-authentication-mode-in-configuration"></a>Para establecer el modo de autenticación en la configuración  
  
1. En el [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento, agregue un [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) .  
  
2. Como elemento secundario, agregue un [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento al `<customBinding>` elemento.  
  
3. Agregue un elemento `<security>` al elemento `<binding>`.  
  
4. Establezca el atributo `authenticationMode` en uno de los valores descritos a continuación. Por ejemplo, el código siguiente define el modo en `AnonymousForCertificate`.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### <a name="to-set-the-mode-programmatically"></a>Para definir el modo mediante programación  
  
1. Determine el tipo de devolución, que puede ser uno de los siguientes: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.SecurityBindingElement>.  
  
2. Llame al método estático apropiado de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>. Por ejemplo, el código siguiente llama al método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3. Utilice el elemento de enlace para crear el enlace personalizado. Para obtener más información, vea [enlaces personalizados](../extending/custom-bindings.md).  
  
## <a name="mode-descriptions"></a>Descripciones de modo  
  
### <a name="anonymousforcertificate"></a>AnonymousForCertificate  

 Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A>. Como alternativa, establezca el `authenticationMode` atributo del elemento <`security`> en `AnonymousForCertificate` .  
  
### <a name="anonymousforsslnegotiated"></a>AnonymousForSslNegotiated  

 Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509 que se negocia en el tiempo de ejecución. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> cuando se pasa un valor `false` para el primer parámetro. Por otra parte, defina el atributo `authenticationMode` en `AnonymousForSslNegotiated`.  
  
### <a name="certificateovertransport"></a>CertificateOverTransport  

 Con este modo de autenticación, el cliente autentica mediante un certificado X.509 que aparece en el nivel de SOAP como un token auxiliar de aprobación; es decir, un token que firma la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `CertificateOverTransport`.  
  
### <a name="issuedtoken"></a>IssuedToken  

 Con este modo de autenticación, el cliente no se autentica al servicio como tal, sino que se autentica a un servicio de token de seguridad y recibe un token de SAML, que presentará a continuación al servidor para demostrar que conoce una clave compartida. El servicio no se autentica en el cliente como tal, sino que el servicio de token de seguridad cifra la clave compartida como parte del token emitido de manera que sólo el servicio puede descifrar la clave. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `IssuedToken`.  
  
### <a name="issuedtokenforcertificate"></a>IssuedTokenForCertificate  

 Con este modo de autenticación, el cliente no se autentica al servicio como tal, sino que se autentica a un servicio de token de seguridad y recibe un token de SAML, que presentará a continuación al servidor para demostrar que conoce una clave compartida. El token emitido aparece en el nivel de SOAP como un token auxiliar de aprobación o un token portador; es decir, un token que firma la firma del mensaje. El servicio autentica al cliente utilizando un certificado X.509. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `IssuedTokenForCertificate`.  
  
### <a name="issuedtokenforsslnegotiated"></a>IssuedTokenForSslNegotiated  

 Con este modo de autenticación, el cliente no se autentica al servicio como tal, sino que se autentica a un servicio de token de seguridad y recibe un token de SAML, que presentará a continuación al servidor para demostrar que conoce una clave compartida. El token emitido aparece en el nivel de SOAP como un token auxiliar de aprobación o un token portador; es decir, un token que firma la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509. El elemento de enlace de seguridad es un <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `IssuedTokenForSslnegotiated`.  
  
### <a name="issuedtokenovertransport"></a>IssuedTokenOverTransport  

 Con este modo de autenticación, el cliente no se autentica al servicio como tal, sino que se autentica a un servicio de token de seguridad y recibe un token de SAML, que presentará a continuación al servidor para demostrar que conoce una clave compartida. El token emitido aparece en el nivel de SOAP como un token auxiliar de aprobación o un token portador; es decir, un token que firma la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte. El elemento de enlace de seguridad es un `TransportSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `IssuedTokenOverTransport`.  
  
### <a name="kerberos"></a>Kerberos  

 Con este modo de autenticación, el cliente se autentica en el servicio utilizando un vale de Kerberos. Ese mismo vale también proporciona autenticación del servidor. El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `Kerberos`.  
  
> [!NOTE]
> Para utilizar este modo de autenticación, la cuenta de servicio debe estar asociada a un nombre de entidad de seguridad de servicio (SPN). Para ello, ejecute el servicio bajo la cuenta de SERVICIO DE RED o la cuenta de SISTEMA LOCAL. Por otra parte, utilice la herramienta SetSpn.exe para crear un SPN para la cuenta de servicio. En cualquier caso, el cliente debe utilizar el SPN correcto en el [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) elemento o mediante el <xref:System.ServiceModel.EndpointAddress> constructor. Para obtener más información, consulte [identidad de servicio y autenticación](service-identity-and-authentication.md).  
  
> [!NOTE]
> Cuando se utiliza el modo de autenticación de `Kerberos`, no se admitirán los niveles de suplantación <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous> y <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.  
  
### <a name="kerberosovertransport"></a>KerberosOverTransport  

 Con este modo de autenticación, el cliente se autentica en el servicio utilizando un vale de Kerberos. El token de Kerberos aparece en el nivel de SOAP como un toque compatible con la aprobación; es decir, un token que firma la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte. El elemento de enlace de seguridad es un `TransportSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `KerberosOverTransport`.  
  
> [!NOTE]
> Para utilizar este modo de autenticación, la cuenta de servicio debe estar asociada con un SPN. Para ello, ejecute el servicio bajo la cuenta de SERVICIO DE RED o la cuenta de SISTEMA LOCAL. Por otra parte, utilice la herramienta SetSpn.exe para crear un SPN para la cuenta de servicio. En cualquier caso, el cliente debe utilizar el SPN correcto en el [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) elemento o mediante el <xref:System.ServiceModel.EndpointAddress> constructor. Para obtener más información, consulte [identidad de servicio y autenticación](service-identity-and-authentication.md).  
  
### <a name="mutualcertificate"></a>MutualCertificate  

 Con este modo de autenticación, el cliente autentica mediante un certificado X.509 que aparece en el nivel de SOAP como un token auxiliar de aprobación; es decir, un token que firma la firma del mensaje. La autenticación del servicio también se realiza mediante un certificado X.509. El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `MutualCertificate`.  
  
### <a name="mutualcertificateduplex"></a>MutualCertificateDuplex  

 Con este modo de autenticación, el cliente autentica mediante un certificado X.509 que aparece en el nivel de SOAP como un token auxiliar de aprobación; es decir, un token que firma la firma del mensaje. La autenticación del servicio también se realiza mediante un certificado X.509. Es enlace es un  `AsymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `MutualCertificateDuplex`.  
  
### <a name="mutualsslnegotiated"></a>MutualSslNegotiated  

 Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509. El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> cuando se pasa un valor `true` para el primer parámetro. Por otra parte, defina el atributo `authenticationMode` en `MutualSslNegotiated`.  
  
### <a name="secureconversation"></a>SecureConversation  

 El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A>. Este método toma <xref:System.ServiceModel.Channels.SecurityBindingElement> como parámetro, que se utiliza durante la inicialización para establecer la sesión segura. Por otra parte, defina el atributo `authenticationMode` en `SecureConversation`.  
  
 Si no se especifica ningún enlace de arranque, se utilizará el modo de autenticación `SspiNegotiated` para el arranque.  
  
### <a name="sspinegotiation"></a>SspiNegotiation  

 Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor. Se utiliza Kerberos si es posible; de lo contrario, se utiliza NT LanMan (NTLM). El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `SspiNegotiated`.  
  
### <a name="sspinegotiatedovertransport"></a>SspiNegotiatedOverTransport  

 Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor. Se utiliza el protocolo Kerberos si es posible; de lo contrario, se utiliza NTLM. El token resultante aparece en el nivel de SOAP como un toque auxiliar de aprobación; es decir, un token que firma la firma del mensaje. El servicio se autentica además en el nivel de transporte por un certificado X.509. El elemento de enlace de seguridad es un `TransportSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `SspiNegotiatedOverTransport`.  
  
### <a name="usernameforcertificate"></a>UserNameForCertificate  

 Con este modo de autenticación, el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en el nivel de SOAP como un token auxiliar firmado; es decir, un token firmado por la firma del mensaje. El servicio autentica al cliente utilizando un certificado X.509. El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `UserNameForCertificate`.  
  
 En el caso del modo de autenticación `UserNameForCertificate`, el cliente y el servicio deben estar utilizando WS-Security 1.1.  
  
### <a name="usernameforsslnegotiated"></a>UserNameForSslNegotiated  

 Con este modo de autenticación, el cliente se autentica mediante un token de nombre de usuario que aparece en el nivel de SOAP como un token auxiliar firmado; es decir, un token firmado por la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509. El elemento de enlace de seguridad es un `SymmetricSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `UserNameForSslNegotiated`.  
  
### <a name="usernameovertransport"></a>UserNameOverTransport  

 Con este modo de autenticación, el cliente se autentica mediante un token de nombre de usuario que aparece en el nivel de SOAP como un token auxiliar firmado; es decir, un token firmado por la firma del mensaje. La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte. El elemento de enlace de seguridad es un `TransportSecurityBindingElement` devuelto por el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A>. Por otra parte, defina el atributo `authenticationMode` en `UserNameOverTransport`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
- [Procedimiento para crear un SecurityBindingElement para un modo de autenticación especificado](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
