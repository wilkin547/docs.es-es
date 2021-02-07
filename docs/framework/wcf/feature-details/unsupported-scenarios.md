---
description: 'Más información acerca de: escenarios no admitidos'
title: Escenarios no admitidos
ms.date: 03/30/2017
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
ms.openlocfilehash: 7547a1acc060a6611a4750e512501cd314bed702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726759"
---
# <a name="unsupported-scenarios"></a>Escenarios no admitidos

Por diversas razones, Windows Communication Foundation (WCF) no admite algunos escenarios de seguridad específicos. Por ejemplo, Windows XP Home Edition no implementa los protocolos de autenticación SSPI o Kerberos y, por tanto, WCF no admite la ejecución de un servicio con la autenticación de Windows en esa plataforma. Se admiten otros mecanismos de autenticación, como el nombre de usuario y la contraseña, y la autenticación integrada HTTP/HTTPS al ejecutar WCF en Windows XP Home Edition.

## <a name="impersonation-scenarios"></a>Escenarios de suplantación

### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>Es posible que la identidad suplantada no fluya cuando los clientes realizan llamadas asincrónicas

 Cuando un cliente realiza llamadas asincrónicas a un servicio WCF usando la autenticación de Windows bajo suplantación, se podría producir la autenticación con la identidad del proceso del cliente en lugar de la identidad suplantada.

### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>Windows XP y cookie de token de contexto seguro habilitados

WCF no admite la suplantación y <xref:System.InvalidOperationException> se produce una excepción cuando se cumplen las condiciones siguientes:

- El sistema operativo es Windows XP.

- El modo de autenticación resulta en una identidad de Windows.

- La propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> de <xref:System.ServiceModel.OperationBehaviorAttribute> está establecida en <xref:System.ServiceModel.ImpersonationOption.Required>.

- Se crea un token de contexto de seguridad (SCT) basado en estado (de forma predeterminada, la creación está deshabilitada).

 El SCT basado en estado solo se puede crear mediante un enlace personalizado. Para obtener más información, consulte [Cómo: crear un token de contexto de seguridad para una sesión segura](how-to-create-a-security-context-token-for-a-secure-session.md). En el código, el token se habilita mediante la creación de un elemento de enlace de seguridad ( <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> ) utilizando el <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> método o y estableciendo el `requireCancellation` parámetro en `false` . El parámetro hace referencia al almacenamiento en caché del SCT. Al establecer el valor en `false`, se habilita la característica del SCT basado en estado.

 Como alternativa, en la configuración, el token se habilita mediante la creación de un> de <`customBinding` , la adición de un elemento de> de <`security` y el establecimiento del `authenticationMode` atributo en SecureConversation y el `requireSecurityContextCancellation` atributo en `true` .

> [!NOTE]
> Los requisitos anteriores son específicos. Por ejemplo, <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> crea un elemento de enlace que resulta en una identidad de Windows, pero no establece un SCT. Por lo tanto, puede usarlo con la `Required` opción en Windows XP.

### <a name="possible-aspnet-conflict"></a>Posible conflicto de ASP.NET

WCF y ASP.NET pueden habilitar o deshabilitar la suplantación. Cuando ASP.NET hospeda una aplicación WCF, puede existir un conflicto entre la configuración de WCF y de la configuración de ASP.NET. En caso de conflicto, la configuración de WCF tiene prioridad, a menos que la <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> propiedad esté establecida en <xref:System.ServiceModel.ImpersonationOption.NotAllowed> , en cuyo caso la configuración de suplantación de ASP.net tiene prioridad.

### <a name="assembly-loads-may-fail-under-impersonation"></a>Se pueden producir errores en las cargas de ensamblado en suplantación

Si el contexto suplantado no tiene los derechos de acceso para cargar un ensamblado y si es la primera vez Common Language Runtime (CLR) intenta cargar el ensamblado para ese AppDomain, el <xref:System.AppDomain> almacena en memoria caché el error. Los siguientes intentos de cargar ese ensamblado (o ensamblados) producirán un error, incluso después de revertir la suplantación e incluso si el contexto revertido tiene derechos de acceso para cargar el ensamblado. Esto se debe a que CLR no vuelve a intentar la carga una vez que se cambia el contexto de usuario. Debe reiniciar el dominio de la aplicación para recuperarse del error.

> [!NOTE]
> El valor predeterminado de la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> de la clase <xref:System.ServiceModel.Security.WindowsClientCredential> es <xref:System.Security.Principal.TokenImpersonationLevel.Identification>. En la mayoría de los casos, un contexto de suplantación del nivel de identificación no tiene derechos para cargar ensamblados adicionales. Éste es el valor predeterminado, por lo que esto se trata de una condición muy común a tener en cuenta. La suplantación del nivel de identificación también tiene lugar cuando el proceso de suplantación no tiene el privilegio `SeImpersonate`. Para obtener más información, consulte [delegación y suplantación](delegation-and-impersonation-with-wcf.md).

### <a name="delegation-requires-credential-negotiation"></a>La delegación requiere la negociación de credenciales

Para utilizar el protocolo de autenticación Kerberos con la delegación, debe implementar el protocolo Kerberos con negociación de credenciales (a veces denominado Kerberos de autenticación mutua o de varios pasos). Si implementa la autenticación de Kerberos sin la negociación de la credencial (denominada en ocasiones Kerberos de "un disparo" o "fase única"), se producirá una excepción. Para obtener más información sobre cómo implementar la negociación de credenciales, consulte [depuración de errores de autenticación de Windows](debugging-windows-authentication-errors.md).

## <a name="cryptography"></a>Criptografía

### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>SHA-256 solo se admite para usos de claves simétricas

WCF admite una variedad de algoritmos de creación de resúmenes de firma y cifrado que se pueden especificar con el conjunto de algoritmos en los enlaces proporcionados por el sistema. Para mejorar la seguridad, WCF admite algoritmos de algoritmo hash seguro (SHA) 2, específicamente SHA-256, para crear hashes de Resumen de firmas. Esta versión admite SHA-256 solo para usos de clave simétrica, como las claves de Kerberos, y donde no se usa un certificado X.509 para firmar el mensaje. WCF no admite firmas RSA (usadas en certificados X. 509) mediante el hash SHA-256 debido a la falta de compatibilidad actual con RSA-SHA256 en WinFX.

### <a name="fips-compliant-sha-256-hashes-not-supported"></a>Hashes SHA-256 conformes con FIPS no admitidos

WCF no admite hashes compatibles con FIPS SHA-256, por lo que WCF no admite los conjuntos de algoritmos que usan SHA-256 en los sistemas donde se requiere el uso de algoritmos compatibles con FIPS.

### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>Se puede producir un error en los algoritmos conformes a FIPS si se edita el registro

Puede habilitar y deshabilitar los algoritmos conformes a los estándares de procesamiento de información federal (FIPS) utilizando el complemento Microsoft Management Console (MMC) de configuración de seguridad local. También puede tener acceso al valor en el registro. Sin embargo, tenga en cuenta que WCF no admite el uso del registro para restablecer la configuración. Si el valor está establecido en algo distinto de 1 ó 0, pueden producirse resultados incoherentes entre el CLR y el sistema operativo.

### <a name="fips-compliant-aes-encryption-limitation"></a>Limitación de cifrado AES compatible con FIPS

El cifrado AES compatible con FIPS no funciona en las devoluciones de llamada dúplex en la suplantación del nivel de identificación.

### <a name="cngksp-certificates"></a>Certificados CNG/KSP

*Cryptography API: Next Generation (CNG)* es el sustituto a largo plazo de CryptoAPI. Esta API está disponible en código no administrado en Windows Vista, Windows Server 2008 y versiones posteriores de Windows.

 .NET Framework 4.6.1 y versiones anteriores no admiten estos certificados porque usan CryptoAPI heredado para administrar los certificados CNG/KSP. El uso de estos certificados con .NET Framework 4.6.1 y versiones anteriores producirá una excepción.

 Hay dos posibles maneras de saber si un certificado utiliza KSP:

- Ejecute `p/invoke` para `CertGetCertificateContextProperty` e inspeccione `dwProvType` en la `CertGetCertificateContextProperty` devuelta.

- Use el  `certutil` comando desde la línea de comandos para consultar los certificados. Para obtener más información, consulte [tareas de certutil para solucionar problemas de certificados](/previous-versions/orphan-topics/ws.10/cc772619(v=ws.10)).

## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>Se produce un error en la seguridad del mensaje si se usa la suplantación ASP.NET y se requiere compatibilidad con ASP.NET

WCF no admite la siguiente combinación de valores de configuración porque puede impedir que se produzca la autenticación del cliente:

- La suplantación de ASP.NET está habilitada. Esto se hace en el archivo de Web.config estableciendo el `impersonate` atributo del elemento de `identity`> <en `true` .

- El modo de compatibilidad de ASP.NET se habilita estableciendo el `aspNetCompatibilityEnabled` atributo de [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) en `true` .

- Se utiliza la seguridad de modo de mensaje.

La solución alternativa consiste en desactivar el modo de compatibilidad de ASP.NET. O bien, si se requiere el modo de compatibilidad ASP.NET, deshabilite la característica de suplantación ASP.NET y use en su lugar la suplantación proporcionada por WCF. Para obtener más información, consulte [delegación y suplantación](delegation-and-impersonation-with-wcf.md).

## <a name="ipv6-literal-address-failure"></a>Error de dirección literal IPv6

Se produce un error en las solicitudes de seguridad cuando el cliente y el servicio están en el mismo equipo y se utilizan direcciones IPv6 literales para el servicio.

 Las direcciones IPv6 literales funcionan si el servicio y el cliente están en equipos diferentes.

## <a name="wsdl-retrieval-failures-with-federated-trust"></a>Errores de recuperación de WSDL con confianza federada

WCF requiere exactamente un documento WSDL para cada nodo de la cadena de confianza federada. Tenga el cuidado de no establecer un bucle al especificar los extremos. Una manera en la que se pueden producir bucles es cuando se utiliza una descarga WSDL de cadenas de confianza federadas con dos o más vínculos en el mismo documento WSDL. Un escenario común donde se puede dar este problema es un servicio federado en el que el servidor de token de seguridad y el servicio se encuentran en el mismo ServiceHost.

 Un ejemplo de esta situación sería un servicio con las tres direcciones de punto de conexión siguientes:

- `http://localhost/CalculatorService/service` (el servicio)

- `http://localhost/CalculatorService/issue_ticket` (STS)

- `http://localhost/CalculatorService/mex` (el extremo de metadatos)

 Esto produce una excepción.

 Puede hacer que este escenario funcione colocando el extremo `issue_ticket` en otra parte.

## <a name="wsdl-import-attributes-can-be-lost"></a>Se pueden perder los atributos de importación de WSDL

WCF pierde la pista de los atributos de un elemento `<wst:Claims>` al hacer una importación de WSDL. Esto ocurre durante una importación de WSDL si `<Claims>``WSFederationHttpBinding.Security.Message.TokenRequestParameters` en lugar de usar directamente las colecciones de tipos de notificación.  Puesto que la importación pierde los atributos, el enlace no efectúa correctamente el viaje de ida y vuelta (round trip) a través de WSDL y por lo tanto es incorrecto en el cliente.

 La solución es modificar el enlace directamente en el cliente después de realizar la importación.

## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Divulgación de información](information-disclosure.md)
- [Elevación de privilegios](elevation-of-privilege.md)
- [Denegación de servicio](denial-of-service.md)
- [Manipulación](tampering.md)
- [Ataques por repetición](replay-attacks.md)
