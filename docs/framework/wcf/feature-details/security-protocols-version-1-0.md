---
title: "Protocolos de seguridad versi&#243;n 1.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Protocolos de seguridad versi&#243;n 1.0
Los protocolos de seguridad de servicios Web proporcionan mecanismos de seguridad de servicios Web que cubren todos los requisitos de seguridad de mensajería para empresas existentes.  En esta sección se describen los detalles de la versión 1.0 de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] \(implementados en el <xref:System.ServiceModel.Channels.SecurityBindingElement>\) para los siguientes protocolos de seguridad de servicios Web.  
  
|||  
|-|-|  
|Especificación\/documento|Link|  
|WSS: Message Security 1,0 de SOAP|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-soap\-message\-security\-1.0.pdf|  
|WSS: Token Profile 1.0 de Username|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-username\-token\-profile\-1.0.pdf|  
|WSS: Token Profile 1,0 de X509|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-x509\-token\-profile\-1.0.pdf|  
|WSS: Token Profile 1.1 de SAML 1,0|http:\/\/docs.oasis\-open.org\/wss\/oasis\-wss\-saml\-token\-profile\-1.0.pdf|  
|WSS: Message Security 1.1 de SOAP|http:\/\/www.oasis\-open.org\/committees\/download.php\/16790\/wss\-v1.1\-spec\-os\-SOAPMessageSecurity.pdf|  
|WSS: Token Profile 1.1 de Username|http:\/\/docs.oasis\-open.org\/wss\/2004\/01\/oasis\-200401\-wss\-username\-token\-profile\-1.0.pdf|  
|WSS: Token Profile 1,1 de X.509|http:\/\/www.oasis\-open.org\/committees\/download.php\/16785\/wss\-v1.1\-spec\-os\-x509TokenProfile.pdf|  
|WSS: Token Profile 1.1 de Kerberos|http:\/\/www.oasis\-open.org\/committees\/download.php\/16788\/wss\-v1.1\-spec\-os\-KerberosTokenProfile.pdf|  
|WSS: Token Profile 1.1 de SAML 1.1|http:\/\/www.oasis\-open.org\/committees\/download.php\/16768\/wss\-v1.1\-spec\-os\-SAMLTokenProfile.pdf|  
|WS\-Secure Conversation|http:\/\/msdn.microsoft.com\/ws\/2005\/02\/ws\-secure\-conversation\/|  
|WS\-Trust|http:\/\/msdn.microsoft.com\/ws\/2005\/02\/ws\-trust\/|  
|Nota de la aplicación:<br /><br /> Uso de WS\-Trust para protocolo de enlace TLS|Para su publicación|  
|Nota de la aplicación:<br /><br /> Uso de WS\-Trust para SPNEGO|Para su publicación|  
|Nota de la aplicación:<br /><br /> Referencias e identidad de extremos de direccionamiento de servicios Web|Para su publicación|  
|WS\-SecurityPolicy 1.1<br /><br /> \(2005\/07\)|http:\/\/msdn.microsoft.com\/ws\/2005\/07\/ws\-security\-policy\/<br /><br /> tal y como se corrigió gracias a las erratas enviadas al comité técnico de WS\-SX OASIS http:\/\/www.oasis\-open.org\/archives\/ws\-sx\/200512\/msg00017.html|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], versión 1, proporciona 17 modos de autenticación que se pueden utilizar como base para la configuración de seguridad de servicios Web.  Cada modo se optimiza para un conjunto común de requisitos de implementación, como:  
  
-   Credenciales utilizadas para autenticar cliente y servicio.  
  
-   Mecanismos de protección de seguridad de transporte o mensaje.  
  
-   Patrones de intercambio de mensajes.  
  
|Modo de autenticación|Autenticación del cliente|Autenticación de servidor|Modo|  
|---------------------------|-------------------------------|-------------------------------|----------|  
|UserNameOverTransport|Nombre de usuario\/contraseña|X509|Transporte|  
|CertificateOverTransport|X509|X509|Transporte|  
|KerberosOverTransport|Windows|X509|Transporte|  
|IssuedTokenOverTransport|Federado|X509|Transporte|  
|SspiNegotiatedOverTransport|Windows SSPI negociado|Windows SSPI negociado|Transporte|  
|AnonymousForCertificate|Ninguna|X509|Mensaje|  
|UserNameForCertificate|Nombre de usuario\/contraseña|X509|Mensaje|  
|MutualCertificate|X509|X509|Mensaje|  
|MutualCertificateDuplex|X509|X509|Mensaje|  
|IssuedTokenForCertificate|Federado|X509|Mensaje|  
|Kerberos|Windows|Windows|Mensaje|  
|IssuedToken|Federado|Federado|Mensaje|  
|SspiNegotiated|Windows SSPI negociado|Windows SSPI negociado|Mensaje|  
|AnonymousForSslNegotiated|Ninguna|X509, TLS\-Nego|Mensaje|  
|UserNameForSslNegotiated|Nombre de usuario\/contraseña|X509, TLS\-Nego|Mensaje|  
|MutualSslNegotiated|X509|X509, TLS\-Nego|Mensaje|  
|IssuedTokenForSslNegotiated|Federado|X509, TLS\-Nego|Mensaje|  
  
 Los extremos que usan tales modos de autenticación pueden expresar sus requisitos de seguridad mediante WS\-SecurityPolicy \(WS\-SP\).  Este documento describe la estructura de mensajes de infraestructura y encabezado de seguridad para cada modo de autenticación y proporciona ejemplos de directivas y mensajes.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] reutiliza WS\-SecureConversation para proporcionar compatibilidad con sesiones seguras para proteger los intercambios de múltiples mensaje entre aplicaciones.  Vea "Sesiones seguras" más abajo para obtener detalles de implementación.  
  
 Además de los modos de autenticación, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona ajustes para controlar mecanismos de protección comunes que se aplican a la mayoría de modos de autenticación basados en seguridad, como, por ejemplo: orden de firma frente a operaciones de cifrado, conjuntos de algoritmos, derivación de claves y confirmación de firmas.  
  
 Los siguientes prefijos y espacios de nombres se utilizan en este documento.  
  
|Prefijo|Espacio de nombres|  
|-------------|------------------------|  
|s|http:\/\/www.w3.org\/2003\/05\/soap\-envelope|  
|sp|http:\/\/schemas.xmlsoap.org\/ws\/2005\/07\/securitypolicy|  
|a|http:\/\/www.w3.org\/2005\/08\/addressing|  
|wsse|TBD – OASIS WSS 1,0 URI|  
|wsse11|TBD – OASIS WSS 1.1 URI|  
|wsu|TBD – OASIS WSS 1.0 Utility URI|  
|ds|TBD – W3C XMLDSig URI|  
|wst|TBD – WS\-Trust 2005\/02 URI|  
|wssc|TBD – WS\-SecureConversation 2005\/02 URI|  
|wsaw|TBD \- Espacio de nombres de directiva WS\-Addressing|  
|wsp|http:\/\/schemas.xmlsoap.org\/ws\/2004\/09\/policy|  
|mssp|http:\/\/schemas.microsoft.com\/ws\/2005\/07\/securitypolicy|  
  
## 1.Perfiles de tokens  
 Las especificaciones Seguridad de Servicios web representan la credencial como tokens de seguridad.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite los siguientes tipos de token:  
  
### 1.1 UsernameToken  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sigue perfiles UsernameToken10 y UsernameToken11 con las restricciones siguientes:  
  
 El atributo R1101 PasswordType en el elemento UsernameToken\\Password no se debe omitir ni debe tener el valor \#PasswordText \(valor predeterminado\).  
  
 Uno puede implementar el \#PasswordDigest mediante extensibilidad.  Se ha observado que \#PasswordDigest se confunde a menudo como un mecanismo de protección de contraseña suficientemente seguro.  Pero \#PasswordDigest no puede actuar como un sustituto del cifrado del UsernameToken.  El objetivo principal de \#PasswordDigest es la protección frente a ataques mediante repetición.  En los modos de autenticación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las amenazas de ataques mediante repetición se mitigan mediante las firmas de mensaje.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] de B1102 nunca emite subelementos Nonce y Created del UsernameToken.  
  
 Estos subelementos están diseñados para ayudar a detectar las repeticiones.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa signaturas de mensaje en su lugar.  
  
 Perfil 1.1 de UsernameToken de seguridad de mensajes SOAP WSS OASIS \(UsernameToken11\) introdujo la característica de derivación de claves a partir de la contraseña.  
  
 La contraseña de UsernameToken B1103 no se debe utilizar para la derivación de claves ni, por consiguiente, para las operaciones criptográficas.  
  
 Razón: las contraseñas generalmente están consideradas demasiado débiles como para ser utilizadas para operaciones criptográficas.  
  
### 1.2 Token X509  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite certificados X509v3 como un tipo de credencial y sigue X509TokenProfile1.0 y X509TokenProfile1.1 con las siguientes restricciones:  
  
 R1201 El atributo ValueType en el elemento BinarySecurityToken debe tener el valor \#X509v3 cuando contiene un certificado X509v3.  
  
 Los perfiles 1.0 y 1.1 de token de WSS X509 también definen \#X509PKIPathv1 y \#PKCS7 como tipos de valor.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no admite estos tipos.  
  
 R1202 Si una extensión SubjectKeyIdentifier \(SKI\) se encuentra en un certificado X509, se debería utilizar wsse:KeyIdentifier para las referencias externas al token, con el atributo ValueType como \#X509SubjectKeyIdentifier, y su contenido el valor codificado en base64 de la extensión SKI del certificado.  
  
 Las referencias SKI se implementan ampliamente y demuestran ser un tipo de referencia externa muy interoperable.  
  
 R1203 Una referencia externa al token de seguridad X509 NO DEBERÍA utilizar ds:X509IssuerSerial.  
  
 R1204 Si se está utilizando X509TokenProfile1.1, una referencia externa al token de seguridad X509 DEBERÍA utilizar la huella digital introducida por WS\-Security 1.1.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite X509IssuerSerial.  Sin embargo, hay problemas de interoperabilidad con X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza una cadena para comparar dos valores de X509IssuerSerial.  Por consiguiente, si uno reordena componentes del Nombre del asunto y envía una referencia a un certificado a un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], puede que no se encuentre.  
  
### 1.3 Token de Kerberos.  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite KerberosTokenProfile1.1 para la autenticación de Windows con las restricciones siguientes:  
  
 R1301 Un Token de Kerberos debe llevar el valor de un AP\_REQ de Kerberos v4 ajustado a GSS, tal y como se define en GSS\_API y en la especificación de Kerberos, y debe tener el atributo ValueType con el valor \#GSS\_Kerberosv5\_AP\_REQ.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza AP\-REQ de Kerberos ajustado a GSS, no un AP\-REQ desnudo.  Éste es un procedimiento de seguridad recomendado.  
  
### 1.4 Token SAML v1.1  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite perfiles de token de WSS SAML 1.0 y 1.1 para tokens SAML v1.1.  Es posible implementar otras versiones de formatos de token SAML.  
  
### 1.5 Token de contexto de seguridad  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el token de contexto de seguridad \(SCT\) introducido en WS\-SecureCoversation.  SCT se utiliza para representar un contexto de seguridad establecido en SecureConversation así como los protocolos de negociación binarios TLS y SSPI, descritos a continuación.  
  
## 2.Parámetros de seguridad de mensajes comunes  
  
### 2.1 Marca de tiempo  
 La presencia de la marca de tiempo se controla mediante la propiedad <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> de la clase <xref:System.ServiceModel.Channels.SecurityBindingElement>.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] serializa siempre wsse:TimeStamp con los campos wsse:Created y wsse:Expires.  El wsse:TimeStamp siempre se firma cuando se utilizan las firmas.  
  
### 2.2 Orden de protección  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite el orden de protección de mensajes "Sign Before Encrypt" \(firmar antes de cifrar\) y "Encrypt Before Sign" \(cifrar antes de firmar\) \(Security Policy 1.1\). "  "Sign Before Encrypt" se recomienda por diferentes motivos, entre los que se incluyen los siguientes: los mensajes protegidos mediante Encrypt Before Sign están expuestos a ataques de sustitución de firmas a menos que se use el mecanismo SignatureConfirmation de WS\-Security 1.1, y una firma sobre el contenido cifrado dificulta la auditoría.  
  
### 2.3 Protección de firmas  
 Cuando se usa Cifrar antes de firmar, se recomienda proteger la firma para evitar los ataques por fuerza bruta para adivinar el contenido cifrado o la clave de la firma \(sobre todo cuando un token personalizado se utiliza con material de clave débil\).  
  
### 2.4 Conjunto de algoritmos  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite todos los conjuntos de algoritmos enumerados en la Directiva de seguridad 1.1.  
  
### 2.5 Derivación de clave  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza la "Derivación de clave para claves simétricas" tal y como se describe en WS\-SecureConversation.  
  
### 2.6 Confirmación de firma  
 La confirmación de firma puede ser como protección frente a ataques de intermediarios para proteger el conjunto de firmas.  
  
### 2.7 Diseño del encabezado de seguridad  
 Cada modo de autenticación describe un cierto diseño para el encabezado de seguridad.  Los elementos dentro del encabezado de seguridad se semiordenan.  Para definir el orden de elementos secundarios del encabezado de seguridad, la directiva WS\-Security define los siguientes modos de diseño del encabezado de seguridad:  
  
|||  
|-|-|  
|Strict|Los elementos se agregan al encabezado de seguridad siguiendo las reglas de diseño descritas en la sección 7.7.1 de la Directiva de seguridad, según un principio general de "declarar antes de usar".|  
|Lax|Los elementos se agregan al encabezado de seguridad en cualquier orden que cumpla con la seguridad de mensajes WSS: SOAP.|  
|LaxTimestampFirst|Igual que Lax, solo que el primer elemento en el encabezado de seguridad debe ser wsse:Timestamp|  
|LaxTimestampLast|Igual que lax, solo que el último elemento en el encabezado de seguridad debe ser wsse:Timestamp|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite los cuatro modos de diseño del encabezado de seguridad.  La estructura de encabezado de Seguridad y los ejemplos de mensajes para los modos de autenticación siguen el modo "Strict" \(estricto\).  
  
## 2.Parámetros de seguridad de mensajes comunes  
 En esta sección se proporcionan ejemplos de directivas para cada modo de autenticación junto con ejemplos que muestran la estructura de encabezado de seguridad en mensajes intercambiados por cliente y servicio.  
  
### 6.1 Protección de transporte  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona cinco modos de autenticación que utilizan el transporte seguro para proteger los mensajes; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport y SspiNegotiatedOverTransport.  
  
 Estos modos de autenticación se construyen utilizando el enlace de transportes descrito en SecurityPolicy.  Para el modo de autenticación de UserNameOverTransport, UsernameToken es un token auxiliar firmado.  Para los otros modos de autenticación el token aparece como un token de endoso firmado.  Los apéndices C.1.2 y C.1.3 de SecurityPolicy describen en detalle el diseño del encabezado de seguridad.  Los siguientes encabezados de seguridad del ejemplo muestran el diseño estricto para un modo de autenticación determinado.  
  
 El valor de propiedad “Derived Keys” para los tokens en todos los casos es "falsa."  
  
 Los valores de las diversas propiedades del enlace de transporte son las siguientes:  
  
 Marca de tiempo: true  
  
 Diseño de encabezado de seguridad: Strict  
  
 Conjunto de algoritmos: Basic256  
  
#### 6.1.1 UsernameOverTransport  
 Con este modo de autenticación, el cliente se autentica con un token de nombre de usuario que aparece en la capa de SOAP como un token auxiliar firmado que siempre se envía desde el iniciador al destinatario.  La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.  El enlace utilizado es un enlace de transporte.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />   
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Diseño del encabezado de seguridad  
  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### 6.1.2 CertificateOverTransport  
 Con este modo de autenticación el cliente se autentica utilizando un certificado X.509 que aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.  La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.  El enlace utilizado es un enlace de transporte.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />   
              <sp:WssX509V3Token10 />   
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Diseño del encabezado de seguridad  
  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### 6.1.3 IssuedTokenOverTransport  
 Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un servicio de token de seguridad \(STS\) y demuestra que conoce una clave compartida.  El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.  La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.  El enlace es un enlace de transporte.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>   
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />   
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Diseño del encabezado de seguridad  
  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### 6.1.4 KerberosOverTransport  
 Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.  El token de Kerberos aparece en la capa de SOAP como un token auxiliar de aprobación.  La autenticación del servicio se realiza mediante un certificado X.509 en el nivel de transporte.  El enlace es un enlace de transporte.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />   
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 Diseño del encabezado de seguridad  
  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### 6.1.5 SspiNegotiatedOverTransport  
 Con este modo de negociación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.  Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.  El SCT resultante aparece en la capa de SOAP como un token auxiliar de aprobación que siempre se envía desde el iniciador al destinatario.  El servicio se autentica además en el nivel de transporte por un certificado X.509.  El enlace utilizado es un enlace de transporte. "  "SPNEGO" \(negociación\) describe cómo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] usa el protocolo de negociación binario SSPI con WS\-Trust.  Los ejemplos de encabezados de seguridad de esta sección tienen lugar una vez se ha establecido SCT mediante el protocolo de enlace SPNEGO.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />   
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />   
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'   
Namespace='http://www.w3.org/2005/08/addressing' />   
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezados de seguridad  
 Una vez se establece el token de contexto de seguridad \(SCT\) a través del protocolo de enlace de SPNEGO mediante negociación binaria WS\-Trust, los mensajes de aplicación tienen encabezados de seguridad con la estructura siguiente.  
  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### 6.2 Uso de certificados X.509 para la autenticación de servicios  
 En esta sección se describen los modos de autenticación siguientes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate y IssuedTokenForCertificate.  
  
#### 6.2.1 MutualCertificate WSS1.0  
 Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.  La autenticación del servicio también se realiza mediante un certificado X.509.  
  
 El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:  
  
 Token del iniciador: el certificado X.509 del cliente, con modo de inclusión establecido en …\/IncludeToken\/AlwaysToRecipient  
  
 Token del destinatario: el certificado X.509 del servidor, con modo de inclusión establecido en …\/IncludeToken\/Never  
  
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Ejemplos de encabezado de seguridad: EncryptBeforeSign  
  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.2.2 MutualCertificateDuplex  
 Con este modo de autenticación el cliente autentica mediante un certificado X.509 que aparece en la capa de SOAP como el token del iniciador.  La autenticación del servicio también se realiza mediante un certificado X.509.  
  
 El enlace usado es un enlace asimétrico con los valores de propiedad siguientes:  
  
 Token del iniciador: certificado X509 de cliente, modo de inclusión establecido en …\/IncludeToken\/AlwaysToRecipient  
  
 Token del destinatario: certificado X509 del servidor, modo de inclusión establecido en …\/IncludeToken\/AlwaysToInitiator  
  
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Solicitud y respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Solicitud y respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.2.3 Uso de SymmetricBinding con autenticación de servicio X.509  
 "WSS10" proporcionó compatibilidad limitada para escenarios con tokens de X509.  Por ejemplo, no hubo manera de proporcionar protección de cifrado y firma para los mensajes que solo usan tokens de X509 de servicio. "  "WSS11" introdujo el uso de EncryptedKey como un token simétrico.  Ahora una clave temporal cifrada para el certificado X.509 de servicio se podría utilizar para la protección de mensajes de solicitud y respuesta.  Los modos de autenticación descritos en la sección 6.4 que se encuentra abajo usan este patrón.  
  
 WS\-SecurityPolicy describe este patrón utilizando SymmetricBinding con token X509 de servicio como el token de protección.  
  
 Los modos de autenticación AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 e IssuedTokenForCertificate usan una instancia similar de sp:SymmetricBinding con los siguientes valores de propiedad:  
  
 Token de protección: certificado X.509 de servidor, modo de inclusión establecido en ...\/IncludeToken\/Never                   
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Los modos de autenticación anteriores solo difieren en los tokens auxiliares que utilizan.  AnonymousForCertificate no tiene ningún token auxiliar, MutualCertificate WSS 1.1 tiene el certificado X509 de cliente como un token auxiliar de aprobación, UserNameForCertificate tiene un token de nombre de usuario como un token auxiliar firmado e IssuedTokenForCertificate tiene el token emitido como un token auxiliar de aprobación.  
  
 Directiva  
  
 Enlace simétrico  
  
```  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token   
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireThumbprintReference />   
                  <sp:WssX509V3Token10 />   
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
          <sp:RequireSignatureConfirmation />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### 6.2.4 AnonymousForCertificate  
 Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.  El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.4.2.  
  
 Directiva  
  
 Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.2.5 UserNameForCertificate  
 Con este modo de autenticación el cliente se autentica en el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.  El servicio autentica al cliente utilizando un certificado X.509.  El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.  
  
 Directiva  
  
 Vea "Directiva" en 6.2.3 más arriba para obtener detalles sobre enlaces  
  
 Token auxiliar firmado  
  
```  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.2.6 MutualCertificate \(WSS 1.1\)  
 Con este modo de autenticación el cliente se autentica mediante un certificado X.509 que aparece en la capa SOAP como el token auxiliar de aprobación.  La autenticación del servicio también se realiza mediante un certificado X.509.  El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.  
  
 Directiva  
  
 Vea Directiva en 6.2.3 para obtener detalles sobre enlaces  
  
 Aprobar token auxiliar  
  
```  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.2.7 IssuedTokenForCertificate  
 Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.  El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.  El servicio autentica al cliente utilizando un certificado X.509.  El enlace utilizado es un enlace simétrico donde el token de protección es una clave generada por el cliente, cifrada con la clave pública del servicio.  
  
 Directiva  
  
 Vea Directiva en 6.2.3 más arriba para obtener detalles sobre enlaces  
  
 Aprobar token auxiliar  
  
```  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />   
       <sp:RequireInternalReference />   
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## 6.3 Kerberos  
 Con este modo de autenticación, el cliente se autentica en el servicio utilizando un tique de Kerberos.  Ese mismo vale también proporciona autenticación del servidor.  El enlace utilizado es un enlace simétrico con las siguientes propiedades:  
  
 Token de protección: vale de Kerberos, modo de inclusión establecido en ...\/IncludeToken\/Once           
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:WssGssKerberosV5ApReqToken11 />   
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### 6.4 IssuedToken  
 Con este modo de autenticación, el cliente no se autentica en el servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.  El servicio no se autentica al cliente como tal, sino que, en su lugar, el STS cifra la clave compartida como parte del token emitido, de manera que solo el servicio puede descifrar la clave.  El enlace utilizado es un enlace simétrico con las siguientes propiedades:  
  
 Token de protección: token emitido, modo de inclusión establecido en ...\/IncludeToken\/AlwaysToRecipient                   
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>   
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:RequireInternalReference />   
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### 6.5 Uso de SslNegotiated para la autenticación de servicio  
 En esta sección se describe un grupo de modos de autenticación que utilizan un enlace simétrico donde el token de protección es un token de contexto de seguridad por WS\-SecureConversation \(WS SC\), cuyo valor de clave se negocia ejecutando el protocolo TLS sobre mensajes de RST\/RSTR de WS\-Trust \(WS\-T\).  En TLSNEGO se describen los detalles de la implementación del protocolo de enlace de TLS mediante WS\-Trust.  Aquí en los ejemplos de mensajes supondremos que SCT con un contexto de seguridad asociado ya se establece a través de un protocolo de enlace.  
  
 El enlace utilizado es un enlace simétrico con las siguientes propiedades:  
  
 Token de protección: SslContextToken, modo de inclusión establecido en ...\/IncludeToken\/Never               
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
#### 6.5.1 Directiva para la autenticación de servicio SslNegotiated  
 La directiva para todos los modos de autenticación de esta sección es similar y solo difieren en los tokens auxiliares firmados o aprobados empleados.  
  
```  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>   
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### 6.5.2 AnonymousForSslNegotiated  
 Con este modo de autenticación, el cliente es anónimo y el servicio se autentica utilizando un certificado X.509.  El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.  
  
 Directiva  
  
 Vea Directiva en 6.5.1 más arriba para obtener detalles sobre enlaces.  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.5.3 UserNameForSslNegotiated  
 Con este modo de autenticación el cliente se autentica el servicio utilizando un token de nombre de usuario que aparece en la capa SOAP como un token auxiliar firmado.  La autenticación del servicio se realiza mediante un certificado X.509.  El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1.  
  
 Directiva  
  
 Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces  
  
 Token auxiliar firmado  
  
```  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />   
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.5.4 IssuedTokenForSslNegotiated  
 Con este modo de autenticación, el cliente no se autentica al servicio como tal; sino que, en su lugar, presenta un token emitido por un STS y demuestra que conoce una clave compartida.  El token emitido aparece en la capa de SOAP como un token auxiliar de aprobación.  La autenticación del servicio se realiza mediante un certificado X.509.  El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.  
  
 Directiva  
  
 Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces  
  
 Aprobar token auxiliar  
  
```  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>   
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />   
        <sp:RequireInternalReference />   
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### 6.5.5 MutualSslNegotiated  
 Con este modo de autenticación, el cliente y el servicio autentican utilizando los certificados X.509.  El enlace utilizado es una instancia de enlace simétrico tal y como se describe en 6.5.1 más arriba.  
  
 Directiva  
  
 Vea la sección 6.5.1 anterior para obtener detalles sobre los enlaces  
  
 Aprobar token auxiliar  
  
```  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />   
        <sp:WssX509V3Token10 />   
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### 6.6 SspiNegotiated  
 Con este modo de autenticación, se usa un protocolo de negociación para realizar la autenticación del cliente y del servidor.  Se utiliza Kerberos si es posible; de lo contrario, se utiliza NTLM.  El enlace utilizado es un enlace simétrico con las siguientes propiedades:  
  
 Token de protección: SpnegoContextToken, modo de inclusión establecido en ...\/IncludeToken\/AlwaysToRecipient               
 Protección de tokens: False  
  
 Encabezado completo y firmas de cuerpo: True  
  
 Orden de protección: SignBeforeEncrypt  
  
 Cifrar firma: True  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### 6.7 SecureConversation  
 El enlace utilizado es un enlace simétrico donde el token de protección es un SCT por WS\-SecureConversation \(WS SC\).  El SCT se negocia mediante WS\-Trust \(WS\-Trust\) o WS\-SecureConversation \(WS\-SC\) según un enlace anidado, que es en sí mismo un enlace simétrico que usa un protocolo de negociación.  El protocolo de negociación utilizará Kerberos para realizar la autenticación de cliente y servidor si es posible.  Si no se puede utilizar Kerberos, se volverá a NTLM.  
  
 Directiva  
  
```  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />   
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />   
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />   
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />   
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />   
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />   
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />   
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />   
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />   
                          <sp:EncryptSignature />   
                          <sp:OnlySignEntireHeadersAndBody />   
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />   
                          <sp:MustSupportRefIssuerSerial />   
                          <sp:MustSupportRefThumbprint />   
                          <sp:MustSupportRefEncryptedKey />   
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />   
                          <sp:RequireClientEntropy />   
                          <sp:RequireServerEntropy />   
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />   
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />   
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />   
          <sp:EncryptSignature />   
          <sp:OnlySignEntireHeadersAndBody />   
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />   
          <sp:MustSupportRefIssuerSerial />   
          <sp:MustSupportRefThumbprint />   
          <sp:MustSupportRefEncryptedKey />   
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />   
          <sp:RequireClientEntropy />   
          <sp:RequireServerEntropy />   
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />   
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### Ejemplos de encabezado de seguridad: SignBeforeEncrypt, EncryptSignature  
 Request  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>    
```  
  
### Ejemplos de encabezado de seguridad: EncryptBeforeSign  
 Request  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 Respuesta  
  
```  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```