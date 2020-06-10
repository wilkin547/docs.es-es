---
title: Elevación de privilegios
ms.date: 03/30/2017
helpviewer_keywords:
- elevation of privilege [WCF]
- security [WCF], elevation of privilege
ms.assetid: 146e1c66-2a76-4ed3-98a5-fd77851a06d9
ms.openlocfilehash: 823b41f86080d4802f76fe69865279a7c3506238
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597415"
---
# <a name="elevation-of-privilege"></a>Elevación de privilegios
La *elevación de privilegios* resulta de conceder a un atacante permisos de autorización más allá de los concedidos inicialmente. Por ejemplo, un atacante con un conjunto de privilegios de permisos de "solo lectura" eleva de algún modo el conjunto para incluir la "lectura y escritura".  
  
## <a name="trusted-sts-should-sign-saml-token-claims"></a>El STS de confianza debería firmar las notificaciones de tokens de SAML  
 Un token del lenguaje de marcado de aserción de seguridad (SAML) es un token XML genérico que es del tipo predeterminado para tokens emitidos. Un servicio de tokens de seguridad (STS) puede construir un token SAML en el que confíe el servicio web final en un intercambio típico. Los tokens SAML contienen las notificaciones en declaraciones. Un atacante puede copiar las notificaciones desde un token válido, crear un nuevo token SAML y firmarlo con un emisor diferente. El objetivo es determinar si el servidor está validando a los emisores y, si no, utilizar esa debilidad para construir tokens SAML que concedan privilegios más allá de los proporcionados por un STS de confianza.  
  
 La clase <xref:System.IdentityModel.Tokens.SamlAssertion> comprueba la firma digital contenida dentro de un token de SAML y el <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> predeterminado necesita que los tokens de SAML estén firmados por un certificado X.509 que sea válido cuando el <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A> de la clase <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> se establezca en <xref:System.ServiceModel.Security.X509CertificateValidationMode.ChainTrust>. El modo `ChainTrust` solo no es suficiente para determinar si el emisor del token de SAML es de confianza. Los servicios que requieren un modelo de confianza más específico pueden usar directivas de autorización y cumplimiento para comprobar el emisor de los conjuntos de notificaciones producidos mediante la autenticación de tokens emitidos o usar los valores de validación X.509 en <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> para restringir el conjunto de certificados de firma permitidos. Para obtener más información, consulte [Administración de notificaciones y autorización con el modelo de identidades](managing-claims-and-authorization-with-the-identity-model.md) y [Federación y tokens emitidos](federation-and-issued-tokens.md).  
  
## <a name="switching-identity-without-a-security-context"></a>Intercambio de identidad sin un contexto de seguridad  
 Lo siguiente se aplica únicamente a WinFX.  
  
 Cuando se establece una conexión entre un cliente y un servidor, la identidad del cliente no cambia, excepto en una situación: después de abrir el cliente WCF, si se cumplen todas las condiciones siguientes:  
  
- Los procedimientos para establecer un contexto de seguridad (mediante una sesión de seguridad de transporte o una sesión de seguridad de mensajes) se desactivan (la <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> propiedad se establece `false` en en caso de seguridad de mensaje o el transporte no es capaz de establecer sesiones de seguridad se utiliza en el caso de seguridad de transporte. HTTPS es un ejemplo de dicho transporte).  
  
- Está utilizando la autenticación de Windows.  
  
- No establece explícitamente la credencial.  
  
- Está llamando al servicio bajo el contexto de seguridad suplantado.  
  
 Si se cumplen estas condiciones, la identidad que se usa para autenticar el cliente en el servicio podría cambiar (puede que no sea la identidad suplantada pero la identidad del proceso en su lugar) después de que se abra el cliente WCF. Esto ocurre porque la credencial de Windows utilizada para autenticar el cliente en el servicio se transmite con cada mensaje, y la credencial utilizada para la autenticación se obtiene a partir de la identidad de Windows del subproceso actual. Si la identidad de Windows del subproceso actual cambia (por ejemplo, suplantando a un llamador diferente), la credencial adjunta al mensaje y utilizada para autenticar el cliente en el servicio también podría cambiar.  
  
 Si desea tener un comportamiento determinista al utilizar la autenticación de Windows junto con la suplantación, debe establecer explícitamente la credencial de Windows o debe establecer un contexto de seguridad con el servicio. Para ello, utilice una sesión de seguridad de mensajes o una sesión de seguridad de transporte. Por ejemplo, el transporte net.tcp puede proporcionar una sesión de seguridad de transporte. Además, debe utilizar solo una versión sincrónica de operaciones de cliente al llamar al servicio. Si establece un contexto de seguridad de mensajes, no debería mantener abierta la conexión con el servicio más tiempo del periodo de renovación de sesión configurado, puesto que la identidad también puede cambiar durante el proceso de renovación de sesión.  
  
### <a name="credentials-capture"></a>Captura de credenciales  
 Lo siguiente se aplica a .NET Framework 3,5 y versiones posteriores.  
  
 Las credenciales utilizadas por el cliente o el servicio se basan en el subproceso de contexto actual. Las credenciales se obtienen cuando se llama al método `Open` (o `BeginOpen`, para las llamadas asincrónicas) del cliente o servicio. Para las clases <xref:System.ServiceModel.ServiceHost> y <xref:System.ServiceModel.ClientBase%601>, los métodos `Open` y `BeginOpen` heredan de los métodos <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> y <xref:System.ServiceModel.Channels.CommunicationObject.BeginOpen%2A> de la clase <xref:System.ServiceModel.Channels.CommunicationObject>.  
  
> [!NOTE]
> Al utilizar el método `BeginOpen`, no se puede garantizar que las credenciales capturadas sean las credenciales del proceso que llama al método.  
  
## <a name="token-caches-allow-replay-using-obsolete-data"></a>Las cachés de tokens permiten la repetición mediante datos obsoletos  
 WCF usa la función de autoridad de seguridad local (LSA) `LogonUser` para autenticar a los usuarios por nombre de usuario y contraseña. Dado que la función Logon es una operación costosa, WCF le permite almacenar en caché los tokens que representan a los usuarios autenticados para aumentar el rendimiento. El mecanismo de almacenamiento en caché guarda los resultados de `LogonUser` para los usos posteriores. Este mecanismo está deshabilitado de forma predeterminada; para habilitarla, establezca la <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CacheLogonTokens%2A> propiedad en `true` o utilice el `cacheLogonTokens` atributo de [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) .  
  
 Puede establecer un período de vida (TTL) para los tokens almacenados en memoria caché estableciendo la propiedad <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.CachedLogonTokenLifetime%2A> en <xref:System.TimeSpan> o utilizar el atributo `cachedLogonTokenLifetime` del elemento `userNameAuthentication`; el valor predeterminado es de 15 minutos. Tenga en cuenta que mientras un token esté almacenado en memoria caché, cualquier cliente que presente el mismo nombre de usuario y contraseña podrá utilizar el token, aunque la cuenta de usuario se elimine de Windows o se haya cambiado su contraseña. Hasta que expire el TTL y el token se quite de la memoria caché, WCF permite que el usuario (posiblemente malintencionado) se autentique.  
  
 Para paliar esto: disminuya la ventana de ataque estableciendo el valor de `cachedLogonTokenLifetime` en el intervalo de tiempo más corto que necesiten sus usuarios.  
  
## <a name="issued-token-authorization-expiration-reset-to-large-value"></a>Autorización de tokens emitidos: restablecimiento de la expiración a un valor mayor  
 Bajo ciertas condiciones, la propiedad <xref:System.IdentityModel.Policy.AuthorizationContext.ExpirationTime%2A> del <xref:System.IdentityModel.Policy.AuthorizationContext> puede establecerse en un valor inesperadamente mayor (el valor del campo <xref:System.DateTime.MaxValue> menos un día o el 20 de diciembre de 9999).  
  
 Esto ocurre al utilizar el <xref:System.ServiceModel.WSFederationHttpBinding> y cualquiera de los enlaces proporcionados por el sistema que tengan un token emitido como el tipo de credencial de cliente.  
  
 Esto también ocurre al crear enlaces personalizados utilizando uno de los siguientes métodos:  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A>  
  
- <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A>  
  
 Para paliar esto, la directiva de autorización debe comprobar la acción y la hora de la expiración de cada directiva de autorización.  
  
## <a name="the-service-uses-a-different-certificate-than-the-client-intended"></a>El Servicio utiliza un certificado diferente del que el cliente pretendía  
 Bajo ciertas condiciones, un cliente puede firmar digitalmente un mensaje con un certificado X.509 y hacer que el servicio recupere un certificado diferente del deseado.  
  
 Esto puede suceder bajo las siguientes circunstancias:  
  
- El cliente firma digitalmente un mensaje mediante un certificado X.509 y no adjunta el certificado X.509 al mensaje, sino que solo hace referencia al certificado utilizando su identificador de clave de sujeto.  
  
- El equipo del servicio contiene dos o más certificados con la misma clave pública, pero contienen información diferente.  
  
- El servicio recupera un certificado que coincide con el identificador de clave de sujeto (SKI), pero no es el que el cliente pensaba utilizar. Cuando WCF recibe el mensaje y comprueba la firma, WCF asigna la información en el certificado X. 509 no deseado a un conjunto de notificaciones que son diferentes y que pueden ser elevadas de lo que esperaba el cliente.  
  
 Para mitigar esto, haga referencia al certificado X.509 de otra manera, como, por ejemplo, mediante <xref:System.ServiceModel.Security.Tokens.X509KeyIdentifierClauseType.IssuerSerial>.  
  
## <a name="see-also"></a>Vea también

- [Consideraciones sobre la seguridad](security-considerations-in-wcf.md)
- [Divulgación de información](information-disclosure.md)
- [Denegación de servicio](denial-of-service.md)
- [Ataques por repetición](replay-attacks.md)
- [Alteración de datos](tampering.md)
- [Escenarios no admitidos](unsupported-scenarios.md)
