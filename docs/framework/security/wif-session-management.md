---
title: "Administraci&#243;n de sesiones de WIF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# Administraci&#243;n de sesiones de WIF
Cuando los intentos de un cliente primero para tener acceso a un recurso protegido hospedado en un usuario de confianza, el cliente primero deben autenticarse a un servicio \(STS\) de token de seguridad que confía el usuario de confianza.  El STS a continuación emite un token de seguridad al cliente.  El cliente muestra este token al usuario de confianza, que se concede el acceso de cliente al recurso protegido.  Sin embargo, no desea que el cliente para tener que re\- autenticar al STS para cada solicitud, especialmente ya que incluso no esté en el mismo equipo o en el mismo dominio que el usuario de confianza.  En su lugar, la base \(WIF\) de la identidad de Windows tiene el cliente y el usuario de confianza establecer una sesión en la que el cliente utiliza un token de seguridad de la sesión para autenticarse al usuario de confianza para todas las solicitudes después de la primera solicitud.  El usuario de confianza puede utilizar este token de seguridad de la sesión, que se almacena en una cookie, para volver a crear <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>de cliente.  
  
 El STS define qué autenticación debe proporcionar el cliente.  Sin embargo, el cliente puede tener varias credenciales con las que puede autenticarse al STS.  Por ejemplo, podría tener un token de Windows Live, un nombre de usuario y una contraseña, un certificado, y un smartkey.  En ese caso, el STS concede a cliente varias identidades, con cada identidad correspondiente a una de las credenciales que el cliente muestra.  El usuario de confianza puede utilizar uno o más de estas identidades cuando decide qué nivel de acceso para conceder al cliente.  
  
 <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=fullName> se utiliza para volver a crear <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>de cliente, que contiene las identidades del cliente en <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A>.  Cada <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> en la colección contiene los tokenes de arranque asociados a esa identidad.  
  
 Si un nuevo token de sesión se emite con el Id. de sesión de token original de la sesión, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=fullName> no actualiza el token de la sesión en la caché de token.  Debe crear instancias siempre un token de sesión con un identificador único de la sesión  
  
> [!NOTE]
>  Session.SecurityTokenHandler.ReadToken produce una excepción de <xref:System.Xml.XmlException> si recibe la entrada no válida; por ejemplo, si está dañado la cookie que contiene el token de la sesión.  Se recomienda detecta esta excepción y proporciona el comportamiento específico de la aplicación.  
  
 Si una página Web protegida contiene a partes de recursos \(como pequeños gráficos\) que también están en el dominio protegido, el cliente debe re\- autenticarse al usuario de confianza para descargar a cada uno de esos recursos.  El uso de un token de autenticación de la sesión se evita la necesidad de autenticar al STS para cada solicitud, pero todavía significa que se están enviando muchas cookies.  Puede configurar la página Web para almacenar los datos y los recursos importantes en el dominio protegido mientras que los elementos de secundaria se almacenan en un dominio desprotegido y se vincula de la página Web principal.  Asimismo, establezca la ruta de acceso de la cookie para hacer referencia al dominio protegido.  
  
 Para trabajar en modo de referencia, Microsoft recomienda el proporcionar de un controlador para el evento de <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated> en el archivo de **global.asax.cs** y el valor de la propiedad de **IsReferenceMode** en el token pasado en la propiedad de <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A> .  Estas actualizaciones se asegurará de que el token de sesión funcione en modo de referencia para cada solicitud y se preferido sobre simplemente establecer la propiedad de <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A> en el módulo de autenticación de la sesión.  
  
## Extensibilidad  
 Puede extender el mecanismo de administración de sesiones.  Una razón de esto sería mejorar el rendimiento.  Por ejemplo, puede crear un controlador personalizado de la cookie que transforma o optimiza el token de seguridad de la sesión entre el estado de en\- memoria y qué entra la cookie.  Para ello, puede configurar la propiedad de <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=fullName> de <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=fullName> para usar un controlador personalizado de la cookie que deriva de <xref:System.IdentityModel.Services.CookieHandler?displayProperty=fullName>.  <xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=fullName> es el controlador predeterminado de la cookie porque las cookies que superan el tamaño permitido para el protocolo HTTP \(Hypertext Transfer Protocol\); si utiliza un controlador personalizado de la cookie en su lugar, debe implementar chunking.  
  
 Para obtener más información, vea [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \(ejemplo de http:\/\/go.microsoft.com\/fwlink\/?LinkID\=248408\).  Este ejemplo muestra la granja caché lista de sesión \(en un tokenreplycache\) para que pueda utilizar sesiones por referencia en lugar de cambiar las grandes cookies; este ejemplo también muestra una manera más fácil de asegurarse de cookies en una granja.  WCF\- se basa la memoria caché de la sesión.  Con respecto a la sesión que garantiza, ilustra una nueva capacidad en WIF 4,5 de una transformación de la cookie basada en MachineKey, que puede activarse simplemente pegando el fragmento de código adecuado del archivo web.config.  El ejemplo propio “no se referencias culturales”, pero muestra lo que necesita para crear la aplicación granja\- lista.