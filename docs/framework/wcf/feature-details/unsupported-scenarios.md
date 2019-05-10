---
title: Escenarios no admitidos
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: 48ed292b3bb22ae4966680805a74b40b249d8a32
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64637748"
---
# <a name="unsupported-scenarios"></a>Escenarios no admitidos
Por diversas razones, Windows Communication Foundation (WCF) no es compatible con algunos escenarios de seguridad específicos. Por ejemplo, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition no implementa los protocolos de autenticación SSPI o Kerberos y, por lo tanto, WCF no admite la ejecución de un servicio con la autenticación de Windows en esa plataforma. Se admiten otros mecanismos de autenticación, como nombre de usuario/contraseña y autenticación de HTTP/HTTPS integrada al ejecutar WCF en Windows XP Home Edition.  
  
## <a name="impersonation-scenarios"></a>Escenarios de suplantación  
  
### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Es posible que la identidad suplantada no fluya cuando los clientes realizan llamadas asincrónicas  
 Cuando un cliente realiza llamadas asincrónicas a un servicio WCF usando la autenticación de Windows bajo suplantación, se podría producir la autenticación con la identidad del proceso del cliente en lugar de la identidad suplantada.  
  
### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP y cookie de token de contexto seguro habilitados  
 WCF no admite la suplantación y un <xref:System.InvalidOperationException> se produce cuando se cumplen las condiciones siguientes:  
  
- El sistema operativo es [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
- El modo de autenticación resulta en una identidad de Windows.  
  
- La propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> de <xref:System.ServiceModel.OperationBehaviorAttribute> se establece en <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
- Se crea un token de contexto de seguridad (SCT) basado en estado (de forma predeterminada, la creación está deshabilitada).  
  
 El SCT basado en estado solo se puede crear mediante un enlace personalizado. Para obtener más información, vea [Cómo: Crear un contexto de seguridad para una sesión segura Token](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).) En código, el token se habilita mediante la creación de un elemento de enlace de seguridad ( <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>) utilizando el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> o <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> y estableciendo el parámetro `requireCancellation` en `false`. El parámetro hace referencia al almacenamiento en caché del SCT. Al establecer el valor en `false`, se habilita la característica del SCT basado en estado.  
  
 Como alternativa, en configuración, el token se habilita mediante la creación de un <`customBinding`>, entonces la adición de un <`security`> elemento y la configuración de la `authenticationMode` atributo en SecureConversation y el `requireSecurityContextCancellation` atribuir a `true`.  
  
> [!NOTE]
>  Los requisitos anteriores son específicos. Por ejemplo, <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> crea un elemento de enlace que resulta en una identidad de Windows, pero no establece un SCT. Por consiguiente, puede utilizarlo con la opción `Required` en [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
### <a name="possible-aspnet-conflict"></a>Posible conflicto de ASP.NET  
 WCF y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] puede habilitar o deshabilitar la suplantación. Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda una aplicación de WCF, puede producirse un conflicto entre WCF y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] opciones de configuración. En el caso de conflicto, la configuración de WCF tiene prioridad, a menos que el <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> propiedad está establecida en <xref:System.ServiceModel.ImpersonationOption.NotAllowed>, en cuyo caso el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] prevalece la configuración de suplantación.  
  
### <a name="assembly-loads-may-fail-under-impersonation"></a>Se puede producir un error en las cargas de ensamblado si se utiliza la suplantación  
 Si el contexto suplantado no tiene los derechos de acceso para cargar un ensamblado y si es la primera vez Common Language Runtime (CLR) intenta cargar el ensamblado para ese AppDomain, el <xref:System.AppDomain> almacena en memoria caché el error. Los siguientes intentos de cargar ese ensamblado (o ensamblados) producirán un error, incluso después de revertir la suplantación e incluso si el contexto revertido tiene derechos de acceso para cargar el ensamblado. Esto se debe a que CLR no vuelve a intentar la carga una vez que el contexto del usuario ha cambiado. Debe reiniciar el dominio de la aplicación para recuperarse del error.  
  
> [!NOTE]
>  El valor predeterminado de la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> de la clase <xref:System.ServiceModel.Security.WindowsClientCredential> es <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. En la mayoría de los casos, un contexto de suplantación del nivel de identificación no tiene derechos para cargar ensamblados adicionales. Éste es el valor predeterminado, por lo que esto se trata de una condición muy común a tener en cuenta. La suplantación del nivel de identificación también tiene lugar cuando el proceso de suplantación no tiene el privilegio `SeImpersonate`. Para obtener más información, consulte [delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### <a name="delegation-requires-credential-negotiation"></a>La delegación requiere la negociación de las credenciales  
 Para utilizar el protocolo de autenticación Kerberos con la delegación, debe implementar el protocolo Kerberos con negociación de credenciales (a veces denominado Kerberos de autenticación mutua o de varios pasos). Si implementa la autenticación de Kerberos sin la negociación de la credencial (denominada en ocasiones Kerberos de "un disparo" o "fase única"), se producirá una excepción. Para obtener más información sobre cómo implementar la negociación de credenciales, vea [depurar errores de autenticación de Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## <a name="cryptography"></a>Criptografía  
  
### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>SHA-256 compatible solo para usos de claves simétricas  
 WCF admite una variedad de cifrado y algoritmos de creación implícita de firma que se pueden especificar mediante el conjunto de algoritmos en los enlaces proporcionados por el sistema. Para mejorar la seguridad, WCF es compatible con los algoritmos del algoritmo de Hash seguro (SHA) 2, en concreto SHA-256, para crear valores hash de síntesis de firma. Esta versión admite SHA-256 solo para usos de clave simétrica, como las claves de Kerberos, y donde no se usa un certificado X.509 para firmar el mensaje. WCF no admite las firmas RSA (utilizadas en certificados X.509) mediante el hash SHA-256 debido a la falta de compatibilidad actual para RSA-SHA256 en la [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### <a name="fips-compliant-sha-256-hashes-not-supported"></a>No se admiten hash SHA-256 conformes a FIPS  
 WCF no admite los hash de SHA-256 compatible con FIPS, por lo que WCF no admite los conjuntos de algoritmos que usan SHA-256 en sistemas donde se requiere el uso de algoritmos que cumplan FIPS.  
  
### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Los algoritmos conformes a FIPS pueden producir errores si se edita el registro  
 Puede habilitar y deshabilitar los algoritmos conformes a los estándares de procesamiento de información federal (FIPS) utilizando el complemento Microsoft Management Console (MMC) de configuración de seguridad local. También puede tener acceso al valor en el registro. Sin embargo, tenga en cuenta que WCF no admite el uso del registro para restablecer la configuración. Si el valor está establecido en algo distinto de 1 ó 0, pueden producirse resultados incoherentes entre el CLR y el sistema operativo.  
  
### <a name="fips-compliant-aes-encryption-limitation"></a>Limitación de cifrado AES conforme a FIPS  
 El cifrado AES conforme a FIPS no funciona en devoluciones de llamada dúplex bajo suplantación del nivel de identificación.  
  
### <a name="cngksp-certificates"></a>Certificados CNG/KSP  
 *API de criptografía: Próxima generación (CNG)* es el sustituto a largo plazo de CryptoAPI. Esta API está disponible en código no administrado en [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)] y versiones posteriores de Windows.  
  
 .NET framework 4.6.1 y versiones anteriores no admiten estos certificados porque usan CryptoAPI heredada para administrar los certificados CNG/KSP. El uso de estos certificados con .NET Framework 4.6.1 y versiones anteriores producirá una excepción.  
  
 Hay dos posibles maneras de saber si un certificado utiliza KSP:  
  
- Ejecute `p/invoke` para `CertGetCertificateContextProperty` e inspeccione `dwProvType` en la `CertGetCertificateContextProperty` devuelta.  
  
- Use la `certutil` línea de comandos desde la línea de comandos para consultar los certificados. Para obtener más información, consulte [tareas de Certutil para solucionar problemas de certificados](https://go.microsoft.com/fwlink/?LinkId=120056).  
  
## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Se produce un error en la seguridad del mensaje si se requiere el uso de suplantación de ASP.NET y compatibilidad de ASP.NET  
 WCF no admite la siguiente combinación de valores porque pueden impedir que se produzca la autenticación cliente:  
  
- [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] La suplantación está habilitada. Esto se hace en el archivo Web.config estableciendo el `impersonate` atributo de la <`identity`> elemento para `true`.  
  
- [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] modo de compatibilidad se habilita estableciendo el `aspNetCompatibilityEnabled` atributo de la [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) a `true`.  
  
- Se utiliza la seguridad de modo de mensaje.  
  
 El método rápido consiste en desactivar el modo de compatibilidad de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. O bien, si la [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se requiere el modo de compatibilidad, deshabilite el [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] suplantación de características y utilice en su lugar la suplantación de proporcionado por WCF. Para obtener más información, consulte [delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## <a name="ipv6-literal-address-failure"></a>Error de dirección literal IPv6  
 Se produce un error en las solicitudes de seguridad cuando el cliente y el servicio están en el mismo equipo y se utilizan direcciones IPv6 literales para el servicio.  
  
 Las direcciones IPv6 literales funcionan si el servicio y el cliente están en equipos diferentes.  
  
## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Errores de recuperación de WSDL con confianza federada  
 WCF requiere exactamente un documento WSDL para cada nodo en la cadena de confianza federada. Tenga el cuidado de no establecer un bucle al especificar los extremos. Una manera en la que se pueden producir bucles es cuando se utiliza una descarga WSDL de cadenas de confianza federadas con dos o más vínculos en el mismo documento WSDL. Un escenario común donde se puede dar este problema es un servicio federado en el que el servidor de token de seguridad y el servicio se encuentran en el mismo ServiceHost.  
  
 Un ejemplo de esta situación sería un servicio con las tres direcciones de punto de conexión siguientes:  
  
- `http://localhost/CalculatorService/service` (el servicio)  
  
- `http://localhost/CalculatorService/issue_ticket` (STS)  
  
- `http://localhost/CalculatorService/mex` (el extremo de metadatos)  
  
 Esto produce una excepción.  
  
 Puede hacer que este escenario funcione colocando el extremo `issue_ticket` en otra parte.  
  
## <a name="wsdl-import-attributes-can-be-lost"></a>Se pueden perder los atributos de importación de WSDL  
 WCF pierde la pista de los atributos de un elemento `<wst:Claims>` de una plantilla`RST` al hacer una importación de WSDL. Esto ocurre durante una importación de WSDL si `<Claims>` se especifica directamente en`WSFederationHttpBinding.Security.Message.TokenRequestParameters` o`IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` en lugar de usar directamente las colecciones de tipos de notificación.  Puesto que la importación pierde los atributos, el enlace no efectúa correctamente el viaje de ida y vuelta (round trip) a través de WSDL y por lo tanto es incorrecto en el cliente.  
  
 La solución es modificar el enlace directamente en el cliente después de realizar la importación.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)
- [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)
- [Elevación de privilegios](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)
- [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)
- [Manipulación](../../../../docs/framework/wcf/feature-details/tampering.md)
- [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
