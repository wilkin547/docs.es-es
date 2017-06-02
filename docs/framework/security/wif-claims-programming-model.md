---
title: "Modelo de programaci&#243;n de notificaciones de WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Modelo de programaci&#243;n de notificaciones de WIF
ASP.NET y Windows Communication Foundation \(WCF\) a los desarrolladores utilizan normalmente las interfaces IIdentity e IPrincipal para trabajar con información de identidad del usuario.  En el.NET 4.5, la Fundación de la identidad de Windows \(WIF\) se ha integrado que reclamaciones ahora están siempre presentes para cualquier principal tal como se ilustra en el diagrama siguiente:  
  
 ![Modelo de programación de notificaciones de WIF](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 En el.NET 4.5, System.Security.Claims contiene las nuevas clases de ClaimsPrincipal y ClaimsIdentity \(ver diagrama anterior\).  Todas las entidades principales de.NET se derivan ahora de ClaimsPrincipal.  Todas las clases de identidad integrados, como FormsIdentity para ASP.NET y WindowsIdentity derivan ahora de ClaimsIdentity.  De forma similar, todas las clases principales integradas como GenericPrincipal y WindowsPrincipal derivan de ClaimsPrincipal.  
  
 Una reclamación es representada por <xref:System.Security.Claims.Claim> clase.  Esta clase tiene las siguientes propiedades importantes:  
  
-   <xref:System.Security.Claims.Claim.Type%2A>representa el tipo de reclamación y suele ser un identificador URI.  Por ejemplo, la notificación de la dirección de correo electrónico se representa como `http://schemas.microsoft.com/ws/2008/06/identity/claims/email`.  
  
-   <xref:System.Security.Claims.Claim.Value%2A>contiene el valor de la solicitud y se representa como una cadena.  Por ejemplo, la dirección de correo electrónico puede representarse como "alguien@contoso.com".  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A>representa el tipo del valor de reclamación y suele ser un identificador URI.  Por ejemplo, el tipo de cadena se representa como `http://www.w3.org/2001/XMLSchema#string`.  El tipo de valor debe ser un QName de acuerdo con el esquema XML.  El valor debe tener el formato `namespace#format` para habilitar WIF generar un valor de tipo QName válido.  Si el espacio de nombres no es un espacio de nombres bien definido, el XML generado probablemente no puede ser esquema validado, porque no habrá un archivo XSD publicado para ese espacio de nombres.  El tipo de valor predeterminado es `http://www.w3.org/2001/XMLSchema#string`.  Por favor, consulte [http:\/\/www.w3.org\/2001\/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155) para los tipos de valor conocido que puede utilizar con seguridad.  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A>es el identificador del servicio de token de seguridad \(STS\) que emitió la reclamación.  Esto se puede representar como dirección URL de el STS o un nombre que representa el STS, tales como `https://sts1.contoso.com/sts`.  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A>es el identificador de el STS que emitió la reclamación, independientemente de cuántos STSs están en la cadena.  Esto se representa como <xref:System.Security.Claims.Claim.Issuer%2A>.  
  
-   <xref:System.Security.Claims.Claim.Subject%2A>es el objeto cuya identidad se está examinando.  Contiene una <xref:System.Security.Claims.ClaimsIdentity>.  
  
-   <xref:System.Security.Claims.Claim.Properties%2A>es un diccionario que permite al desarrollador proporcionar transferir en el cable junto con las demás propiedades de datos específicos de la aplicación y puede utilizarse para la validación personalizada.  
  
## Delegación de identidad  
 Una propiedad importante de <xref:System.Security.Claims.ClaimsIdentity> es <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>.  Esta propiedad permite la delegación de credenciales en un sistema de varios niveles en el que un nivel medio actúa como el cliente para realizar solicitudes a un servicio de back\-end.  
  
### Acceso a las reclamaciones a través de Thread.CurrentPrincipal  
 Para tener acceso a conjunto del usuario actual de solicitudes en una aplicación de punto de reunión, utilice `Thread.CurrentPrincipal`.  
  
 Ejemplo de código siguiente muestra el uso de este método para obtener un System.Security.Claims.ClaimsIdentity:  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
```  
  
 Para obtener más información, vea <xref:System.Security.Claims>.  
  
### Tipo de notificación de papel  
 Es parte de la configuración de la aplicación de punto de reunión determinar lo que su función debe ser el tipo de notificación.  System.Security.Claims.ClaimsPrincipal.IsInRole\(System.String\) utiliza este tipo de notificación.  El tipo de notificación predeterminado es `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.  
  
### Reclamaciones que se extrae por la Fundación de la identidad de Windows desde distintos tipos de símbolo \(token\)  
 WIF es compatible con varias combinaciones de mecanismos de autenticación de la caja.  En la tabla siguiente incluye las notificaciones que WIF se extrae de diferentes tipos de token.  
  
||||  
|-|-|-|  
|Tipo de símbolo \(token\)|Reclamación generado|Mapa de Token de acceso de Windows|  
|SAML 1.1|1.  Todas las solicitudes de System.IdentityModel.SecurityTokenService.GetOutputClaimsIdentity\(System.Security.Claims.ClaimsPrincipal,System.IdentityModel.Protocols.WSTrust.RequestSecurityToken,System.IdentityModel.Scope\).<br />2.  El `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey` notificación que contiene la serialización XML de la clave de confirmación, si el símbolo \(token\) contiene un token de prueba.<br />3.  El `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername` de notificación desde el elemento de emisor.<br />4.  AuthenticationMethod AuthenticationInstant reclamaciones y, si el símbolo \(token\) contiene una instrucción de autenticación.|Además de las reclamaciones enumeradas en "SAML 1.1", excepto las reclamaciones de tipo `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, relacionados con la autenticación de Windows se agregarán las reclamaciones y la identidad se representará mediante WindowsClaimsIdentity.|  
|SAML 2.0|Igual que "SAML 1.1".|Igual que "SAML 1.1 asignado a la cuenta de Windows".|  
|X509|1.  Reclamaciones con X 500 distinguen nombre, nombrecorreoelectrónico, dnsName, SimpleName, UpnName, UrlName, huella digital, RsaKey \(Esto puede extraerse mediante el método RSACryptoServiceProvider.ExportParameters de la propiedad X509Certificate2.PublicKey.Key\), DsaKey \(Esto puede extraerse mediante el método DSACryptoServiceProvider.ExportParameters de la propiedad X509Certificate2.PublicKey.Key\), propiedades de número de serie de X 509 Certificate.<br />2.  Reclamación AuthenticationMethod con valor de `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`.  Reclamación de AuthenticationInstant con el valor de la hora cuando se validó el certificado en formato de fecha y hora de esquema XML.|1.  Utiliza el nombre de dominio completo de cuenta de Windows como el `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name` valor de notificación.  .<br />2.  Las reclamaciones de la X 509 no se asigna el certificado para Windows y las reclamaciones de la cuenta de windows obtenidos mediante la asignación de certificado para Windows.|  
|UPN|1.  Las notificaciones son similares a las reclamaciones de la sección de autenticación de Windows.<br />2.  Reclamación AuthenticationMethod con valor de `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`.  La notificación de AuthenticationInstant con el valor de la hora cuando se validó la contraseña en formato de fecha y hora de esquema XML.||  
|Windows \(Kerberos o NTLM\)|1.  Notificaciones generados desde el token de acceso tales como: PrimarySID, DenyOnlyPrimarySID, PrimaryGroupSID, DenyOnlyPrimaryGroupSID, GroupSID, DenyOnlySID y el nombre<br />2.  AuthenticationMethod con el valor `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`.  AuthenticationInstant con el valor de la hora al Windows tener acceso al símbolo \(token\) se creó en el formato de fecha y hora de esquema XML.||  
|Par de claves RSA|1.  El `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` de notificación con el valor de RSAKeyValue.<br />2.  Reclamación AuthenticationMethod con el valor `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`.  Reclamación de AuthenticationInstant con el valor de la hora en que fue autenticada por la clave RSA \(es decir, se comprobó la firma\) en el formato de fecha y hora de esquema XML.||  
  
|||  
|-|-|  
|Tipo de autenticación|Identificador URI que se emite en Reclamación de "AuthenticationMethod"|  
|Contraseña|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|Sin especificar|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|