---
title: "Escenarios no admitidos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
caps.latest.revision: 43
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# Escenarios no admitidos
Por varias razones, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] no admite algunos escenarios de seguridad concretos. Por ejemplo, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition no implementa los protocolos de autenticación SSPI o Kerberos y, por consiguiente, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no permite ejecutar un servicio con autenticación de Windows en esa plataforma. Se admiten otros mecanismos de autenticación, como el uso de nombre de usuario\/contraseña y la autenticación HTTP\/HTTPS integrada al ejecutar [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en Windows XP Home Edition.  
  
## Escenarios de suplantación  
  
### Es posible que la identidad suplantada no fluya cuando los clientes realizan llamadas asincrónicas  
 Cuando un cliente realiza llamadas asincrónicas a un servicio WCF usando la autenticación de Windows bajo suplantación, se podría producir la autenticación con la identidad del proceso del cliente en lugar de la identidad suplantada.  
  
### Windows XP y cookie de token de contexto seguro habilitados  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite la suplantación. Se producirá una excepción <xref:System.InvalidOperationException> en las siguientes condiciones:  
  
-   El sistema operativo es [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
-   El modo de autenticación resulta en una identidad de Windows.  
  
-   La propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> de <xref:System.ServiceModel.OperationBehaviorAttribute> se establece en <xref:System.ServiceModel.ImpersonationOption>.  
  
-   Se crea un token de contexto de seguridad \(SCT\) basado en estado \(de forma predeterminada, la creación está deshabilitada\).  
  
 El SCT basado en estado solo se puede crear mediante un enlace personalizado.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Cómo: Crear un token de contexto de seguridad para una sesión segura](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)\). En código, el token se habilita mediante la creación de un elemento de enlace de seguridad \( <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> o <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>\) utilizando el método <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=fullName> o <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=fullName> y estableciendo el parámetro `requireCancellation` en `false`. El parámetro hace referencia al almacenamiento en caché del SCT. Al establecer el valor en `false`, se habilita la característica del SCT basado en estado.  
  
 De manera alternativa, en la configuración, el token se habilita mediante la creación de un elemento \<`customBinding`\>, agregando después un elemento \<`security`\> y estableciendo el atributo `authenticationMode` en SecureConversation y el atributo `requireSecurityContextCancellation` en `true`.  
  
> [!NOTE]
>  Los requisitos anteriores son específicos. Por ejemplo, <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> crea un elemento de enlace que resulta en una identidad de Windows, pero no establece un SCT. Por consiguiente, puede utilizarlo con la opción `Required` en [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
### Posible conflicto de ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] pueden habilitar o deshabilitar la suplantación. Cuando [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] hospeda una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede producirse un conflicto entre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y los ajustes de configuración de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. En caso de conflicto, el valor de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tiene preferencia, a menos que la propiedad <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> esté establecida en <xref:System.ServiceModel.ImpersonationOption>, en cuyo caso el valor de suplantación [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] tiene preferencia.  
  
### Se puede producir un error en las cargas de ensamblado si se utiliza la suplantación  
 Si el contexto suplantado no tiene los derechos de acceso para cargar un ensamblado y si es la primera vez Common Language Runtime \(CLR\) intenta cargar el ensamblado para ese AppDomain, el <xref:System.AppDomain> almacena en memoria caché el error. Los siguientes intentos de cargar ese ensamblado \(o ensamblados\) producirán un error, incluso después de revertir la suplantación e incluso si el contexto revertido tiene derechos de acceso para cargar el ensamblado. Esto se debe a que CLR no vuelve a intentar la carga una vez que el contexto del usuario ha cambiado. Debe reiniciar el dominio de la aplicación para recuperarse del error.  
  
> [!NOTE]
>  El valor predeterminado de la propiedad <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> de la clase <xref:System.ServiceModel.Security.WindowsClientCredential> es <xref:System.Security.Principal.TokenImpersonationLevel>. En la mayoría de los casos, un contexto de suplantación del nivel de identificación no tiene derechos para cargar ensamblados adicionales. Éste es el valor predeterminado, por lo que esto se trata de una condición muy común a tener en cuenta. La suplantación del nivel de identificación también tiene lugar cuando el proceso de suplantación no tiene el privilegio `SeImpersonate`.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
### La delegación requiere la negociación de las credenciales  
 Para utilizar el protocolo de autenticación Kerberos con la delegación, debe implementar el protocolo Kerberos con negociación de credenciales \(a veces denominado Kerberos de autenticación mutua o de varios pasos\). Si implementa la autenticación de Kerberos sin la negociación de la credencial \(denominada en ocasiones Kerberos de "un disparo" o "fase única"\), se producirá una excepción.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] cómo implementar la negociación de credenciales, consulte [Depuración de errores de autenticación de Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md).  
  
## Criptografía  
  
### SHA\-256 compatible solo para usos de claves simétricas  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite una variedad de algoritmos de creación de resúmenes de firma y cifrado que puede especificar utilizando el conjunto de algoritmos en los enlaces proporcionados por el sistema. Para una mayor seguridad, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite algoritmos de hash seguro \(SHA\) 2, en concreto SHA\-256, para crear los hash de resumen de firma. Esta versión admite SHA\-256 solo para usos de clave simétrica, como las claves de Kerberos, y donde no se usa un certificado X.509 para firmar el mensaje.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite las signaturas de RSA \(usadas en certificados X.509\) mediante el hash SHA\-256 debido a la falta actual de compatibilidad con RSA\-SHA256 en [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].  
  
### No se admiten hash SHA\-256 conformes a FIPS  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite los hash conformes a SHA\-256 FIPS, por lo que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite los conjuntos de algoritmos que usan SHA\-256 en sistemas donde se requiere el uso de algoritmos conformes a FIPS.  
  
### Los algoritmos conformes a FIPS pueden producir errores si se edita el registro  
 Puede habilitar y deshabilitar los algoritmos conformes a los estándares de procesamiento de información federal \(FIPS\) utilizando el complemento Microsoft Management Console \(MMC\) de configuración de seguridad local. También puede tener acceso al valor en el registro. Tenga en cuenta, sin embargo, que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no permite utilizar el registro para restablecer el valor. Si el valor está establecido en algo distinto de 1 ó 0, pueden producirse resultados incoherentes entre el CLR y el sistema operativo.  
  
### Limitación de cifrado AES conforme a FIPS  
 El cifrado AES conforme a FIPS no funciona en devoluciones de llamada dúplex bajo suplantación del nivel de identificación.  
  
### Certificados CNG\/KSP en Windows Server 2008  
 La *API de criptografía de nueva generación \(CNG\)* sustituirá a largo plazo CryptoAPI. Esta API está disponible en código no administrado en [!INCLUDE[wv](../../../../includes/wv-md.md)] y [!INCLUDE[lserver](../../../../includes/lserver-md.md)].  
  
 En plataformas de nivel inferior \([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)]\) .NET Framework 2.0 no reconoce este protocolo y en su lugar utiliza la *CryptoApi* heredada para administrar los certificados CNG\/KSP. En [!INCLUDE[lserver](../../../../includes/lserver-md.md)] y [!INCLUDE[wv](../../../../includes/wv-md.md)], .NET Framework 3.5 no admite estos certificados: su uso produce una excepción.  
  
 Hay dos posibles maneras de saber si un certificado utiliza KSP:  
  
-   Ejecute `p/invoke` para `CertGetCertificateContextProperty` e inspeccione `dwProvType` en la `CertGetCertificateContextProperty` devuelta.  
  
-   Use el comando `certutil` desde la línea de comandos para consultar los certificados.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Tareas de CertUtil para solucionar problemas relacionados con los certificados](http://go.microsoft.com/fwlink/?LinkId=120056).  
  
## Se produce un error en la seguridad del mensaje si se requiere el uso de suplantación de ASP.NET y compatibilidad de ASP.NET  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite la combinación siguiente de valores porque pueden evitar que se produzca la autenticación del cliente:  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] La suplantación está habilitada. Esto se logra en el archivo Web.config estableciendo el atributo `impersonate` del elemento \<`identity`\> en `true`.  
  
-   El modo de compatibilidad de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] se habilita estableciendo el atributo `aspNetCompatibilityEnabled` de [\<serviceHostingEnvironment\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) en `true`.  
  
-   Se utiliza la seguridad de modo de mensaje.  
  
 El método rápido consiste en desactivar el modo de compatibilidad de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]. O, si se requiere el modo de compatibilidad de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], deshabilite la característica de suplantación de [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] y utilice en su lugar la suplantación proporcionada por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Delegación y suplantación](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
## Error de dirección literal IPv6  
 Se produce un error en las solicitudes de seguridad cuando el cliente y el servicio están en el mismo equipo y se utilizan direcciones IPv6 literales para el servicio.  
  
 Las direcciones IPv6 literales funcionan si el servicio y el cliente están en equipos diferentes.  
  
## Errores de recuperación de WSDL con confianza federada  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requiere exactamente un documento WSDL para cada nodo en la cadena de confianza federada. Tenga el cuidado de no establecer un bucle al especificar los extremos. Una manera en la que se pueden producir bucles es cuando se utiliza una descarga WSDL de cadenas de confianza federadas con dos o más vínculos en el mismo documento WSDL. Un escenario común donde se puede dar este problema es un servicio federado en el que el servidor de token de seguridad y el servicio se encuentran en el mismo ServiceHost.  
  
 Un ejemplo de esta situación sería un servicio con las tres direcciones de extremo siguientes:  
  
-   http:\/\/localhost\/CalculatorService\/service \(el servicio\)  
  
-   http:\/\/localhost\/CalculatorService\/issue\_ticket \(STS\)  
  
-   http:\/\/localhost\/CalculatorService\/mex \(extremo de metadatos\)  
  
 Esto produce una excepción.  
  
 Puede hacer que este escenario funcione colocando el extremo `issue_ticket` en otra parte.  
  
## Se pueden perder los atributos de importación de WSDL  
 WCF pierde la pista de los atributos de un elemento `<wst:Claims>` de una plantilla `RST` al hacer una importación de WSDL. Esto ocurre durante una importación de WSDL si `<Claims>` se especifica directamente en `WSFederationHttpBinding.Security.Message.TokenRequestParameters` o en `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters` en lugar de usar directamente las colecciones de tipos de notificación.  Puesto que la importación pierde los atributos, el enlace no efectúa correctamente el viaje de ida y vuelta \(round trip\) a través de WSDL y por lo tanto es incorrecto en el cliente.  
  
 La solución es modificar el enlace directamente en el cliente después de realizar la importación.  
  
## Vea también  
 [Consideraciones de seguridad](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)   
 [Divulgación de información](../../../../docs/framework/wcf/feature-details/information-disclosure.md)   
 [Elevación de privilegio](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)   
 [Denegación de servicio](../../../../docs/framework/wcf/feature-details/denial-of-service.md)   
 [Manipulación](../../../../docs/framework/wcf/feature-details/tampering.md)   
 [Ataques por repetición](../../../../docs/framework/wcf/feature-details/replay-attacks.md)