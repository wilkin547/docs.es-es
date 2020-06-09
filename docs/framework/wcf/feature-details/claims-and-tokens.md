---
title: Notificaciones y tokens
ms.date: 03/30/2017
helpviewer_keywords:
- claims [WCF], and tokens
ms.assetid: eff167f3-33f8-483d-a950-aa3e9f97a189
ms.openlocfilehash: cbc97f2224bce640757e1cef88fe325db477cfd7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84587032"
---
# <a name="claims-and-tokens"></a>Notificaciones y tokens

En este tema se describen los distintos tipos de notificaciones que Windows Communication Foundation (WCF) crea a partir de los tokens predeterminados que admite.

Puede examinar las notificaciones de una credencial del cliente mediante <xref:System.IdentityModel.Claims.ClaimSet> y las clases <xref:System.IdentityModel.Claims.Claim>. `ClaimSet` contiene una colección de objetos `Claim`. Cada `Claim` posee los siguientes miembros importantes:

- La propiedad <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> devuelve un Identificador uniforme de recursos (URI) que especifica el tipo de notificación que se realiza. Por ejemplo, un tipo de demanda puede ser una huella digital de un certificado, en cuyo caso el URI es `http://schemas.microsoft.com/ws/20005/05/identity/claims/thumprint` .

- La propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> devuelve una dirección URI que especifica el derecho de la notificación. Los derechos predefinidos se encuentran en la clase (<xref:System.IdentityModel.Claims.Rights>, <xref:System.IdentityModel.Claims.Rights.Identity%2A>) <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>.

- La propiedad <xref:System.IdentityModel.Claims.Claim.Resource%2A> devuelve el recurso asociado con la notificación.

Cada <xref:System.IdentityModel.Claims.ClaimSet> también posee una propiedad <xref:System.IdentityModel.Claims.ClaimSet.Issuer%2A>, que representa el <xref:System.IdentityModel.Claims.ClaimSet> de `Issuer`.

## <a name="windows-accounts"></a>Cuentas de Windows

Cuando una credencial del cliente se asigna a una cuenta de usuario de Windows, el <xref:System.IdentityModel.Claims.ClaimSet> resultante adopta los siguientes valores:

- `Issuer` es el valor devuelto por la propiedad estática de Windows de la clase <xref:System.IdentityModel.Claims.ClaimSet>.

- Las notificaciones de la colección son:

  - <xref:System.IdentityModel.Claims.Claim> con un valor <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> de identificador de seguridad (SID), un valor de propiedad <xref:System.IdentityModel.Claims.Claim.Right%2A> de `Identity`. y <xref:System.IdentityModel.Claims.Claim.Resource%2A> que devuelve el valor SID real. Un SID es un valor único que emite el controlador de dominio para cada usuario. El SID se utiliza para identificar al usuario en interacciones con seguridad de Windows.

  - <xref:System.IdentityModel.Claims.Claim> con un valor <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> de SID, <xref:System.IdentityModel.Claims.Claim.Right%2A> de `PossessProperty`, y <xref:System.IdentityModel.Claims.Claim.Resource%2A> del valor SID.

  - Una <xref:System.IdentityModel.Claims.Claim> con un <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> de <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A>, un <xref:System.IdentityModel.Claims.Claim.Right%2A> de `PossessProperty`, y un <xref:System.IdentityModel.Claims.Claim.Resource%2A> de cadena que contiene el nombre de usuario (por ejemplo, "MYMACHINE\Bob").

  - Notificaciones SID adicionales con <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> para los distintos grupos a los que pertenece el usuario.

## <a name="certificates"></a>Certificados

Cuando la credencial del cliente es un certificado, el <xref:System.IdentityModel.Claims.ClaimSet> resultante tiene los siguientes valores:

- Para los certificados de emisión propia, `Issuer` es el propio <xref:System.IdentityModel.Claims.ClaimSet>. El <xref:System.IdentityModel.Claims.ClaimSet> devuelve <xref:System.IdentityModel.Claims.Claim.ClaimType%2A> de <xref:System.IdentityModel.Claims.ClaimTypes.Thumbprint%2A>, un <xref:System.IdentityModel.Claims.Claim.Right%2A> de `Identity`, y un valor <xref:System.IdentityModel.Claims.Claim.Resource%2A> que es una matriz <xref:System.Byte> que contiene la huella digital del certificado.

- Para un certificado emitido por una entidad de certificación, el emisor es el `ClaimSet` que representa el certificado de la entidad de certificación.

- Las `Claims` de la colección incluyen.

  - Una `Claim` con un `ClaimType` de huella digital, un `Right` PossessProperty, y un `Resource` que es una matriz de bytes que contiene la huella digital del certificado.

  - Las notificaciones PossessProperty adicionales de varios tipos, incluidas X500DistinguishedName, Dns, Name, Upn y Rsa, representan varias propiedades del certificado. El recurso para la declaración de RSA es la clave pública asociada al certificado. **Nota:** Si el tipo de credencial de cliente es un certificado que el servicio asigna a una cuenta de Windows, `ClaimSet` se generan dos objetos. El primero contiene todas las notificaciones relacionadas con la cuenta de Windows, y el segundo todas las notificaciones relacionadas con el certificado.

## <a name="user-namepassword"></a>Nombre de usuario/contraseña

Cuando la credencial del cliente es un nombre de usuario/contraseña (o equivalente) que no se asigna a una cuenta de Windows, el `ClaimSet` resultante es emitido por la propiedad <xref:System.IdentityModel.Claims.ClaimSet.System%2A> estática de la clase `ClaimSet`. `ClaimSet`Contiene una `Identity` demanda de tipo <xref:System.IdentityModel.Claims.ClaimTypes.Name%2A> cuyo recurso es el nombre de usuario que proporciona el cliente. Una notificación correspondiente tiene un `Right` de `PossessProperty`.

## <a name="rsa-keys"></a>Claves RSA

Cuando se utiliza una clave RSA no asociada con un certificado, el resultante `ClaimSet` se emite automáticamente y contiene una `Identity` demanda de tipo <xref:System.IdentityModel.Claims.ClaimTypes.Rsa%2A> cuyo recurso es la clave RSA. Una notificación correspondiente tiene un `Right` de `PossessProperty`.

## <a name="saml"></a>SAML

Cuando el cliente realiza la autenticación con un token de Lenguaje de marcado de aserciones de seguridad (SAML), la entidad que firmo el token de SAML, con frecuencia el certificado del servicio de token de seguridad (STS) que emitió el token de SAML, emite el `ClaimSet` resultante. El `ClaimSet` contiene varias notificaciones tal y como se encuentran en el token de SAML. Si el token de SAML contiene `SamlSubject` con un no nombre `null`, se crea una notificación `Identity` con un tipo de <xref:System.IdentityModel.Claims.ClaimTypes.NameIdentifier%2A>, y un tipo de recurso <xref:System.IdentityModel.Tokens.SamlNameIdentifierClaimResource>.

## <a name="identity-claims-and-servicesecuritycontextisanonymous"></a>Notificaciones de identidad y ServiceSecurityContext.IsAnonymous

Si ninguno de los `ClaimSet` objetos resultantes de las credenciales del cliente contiene una claim con un `Right` de `Identity,` , la <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A> propiedad devuelve `true` . Si una o más de esas notificaciones están presentes, la propiedad `IsAnonymous` devuelve `false`.

## <a name="see-also"></a>Vea también

- <xref:System.IdentityModel.Claims.ClaimSet>
- <xref:System.IdentityModel.Claims.Claim>
- <xref:System.IdentityModel.Claims.Rights>
- <xref:System.IdentityModel.Claims.ClaimTypes>
- [Administración de notificaciones y autorización con el modelo de identidad](managing-claims-and-authorization-with-the-identity-model.md)
