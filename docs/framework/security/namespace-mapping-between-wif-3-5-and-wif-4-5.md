---
title: "Asignaci&#243;n de espacio de nombres entre WIF 3.5 y WIF 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# Asignaci&#243;n de espacio de nombres entre WIF 3.5 y WIF 4.5
A partir de.NET 4,5, la base \(WIF\) de la identidad de Windows se ha integrado totalmente en .NET Framework.  Esta integración engendró cambios de nombre y alguna consolidación de los espacios de nombres WIF y de la superficie de la API.  Este tema ofrece cierta orientación y una asignación general entre los espacios de nombres WIF 3,5 y los espacios de nombres WIF 4,5.  No pretende ser exhaustiva, pero proporciona suficiente información general sobre dónde buscar clases familiares de WIF 3,5 en WIF 4,5.  Para obtener información detallada sobre las diferencias entre WIF 3,5 y WIF 4,5, vea [Novedades de Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md).  Para obtener instrucciones sobre cómo migrar las aplicaciones compiladas con WIF 3,5 a WIF 4,5, vea [Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md).  
  
## Asignación de espacio de nombres WIF 3,5 a de WIF 4,5  
 Las clases de WIF, que se recogieron en los espacios de nombres de `Microsoft.IdentityModel` en WIF 3,5, ahora se distribuyen entre los espacios de nombres siguientes: `System.Security.Claims`, `System.ServiceModel.Security`, y los espacios de nombres de `System.IdentityModel` en WIF 4,5.  Además los espacios de nombres de algún WIF 3,5 se consolidados o quitarán completamente en WIF 4,5.  
  
> [!IMPORTANT]
>  Los siguientes espacios de nombres de `System.IdentityModel` contienen clases que implementan el modelo de identidad demanda\- basado WCF: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName>, y <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  El modelo de identidad demanda\- basado WCF se reemplaza por WIF.  No debe utilizar clases de estos tres espacios de nombres al compilar soluciones basadas en WIF.  
  
 La tabla siguiente proporciona información sobre donde las clases de WIF 3,5 se encuentran en WIF 4,5.  
  
||||  
|-|-|-|  
|**Espacio de nombres WIF 3,5**|**Espacio de nombres WIF 4,5**|**Comentarios**|  
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=fullName>|-   La mayoría de las clases que representan constantes no se implementan.<br />-   Las clases que se utilizan para compilar servicios de token de seguridad se han movido de `Microsoft.IdentityModel.SecurityTokenService` a <xref:System.IdentityModel?displayProperty=fullName>.<br />-   Las clases de `Microsoft.IdentityModel.Threading` se han movido a <xref:System.IdentityModel?displayProperty=fullName>.<br />-   Las clases de `ExceptionMapper` y de `MruSecurityTokenCache` no se implementan.|  
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=fullName>|-   Las interfaces de `IClaimsPrincipal` y de `IClaimsIdentity` no se implementan en WIF 4,5.  En su lugar <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> y <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> ahora son clases base de la que la mayoría de las clases de entidad de seguridad y la identidad de .NET derivan.  Esto significa que no hay necesidad de las peticiones especializadas entidad de seguridad y las clases de identidad como `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` y `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` en WIF 4,5, el uso <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> y <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> en su lugar.  Lo mismo sucede con otro para las otras peticiones especializadas entidad de seguridad y las clases de identidad que existían en WIF 3,5.<br />-   La clase de `Microsoft.IdentityModel.Claims.ClaimsCollection` no se implementa en WIF 4,5.  En su lugar, las colecciones de peticiones se exponen como colecciones enumerables de <xref:System.Security.Claims.Claim?displayProperty=fullName>escrito.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName> y <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> proporcionan métodos que ahora LINQ son totalmente compatibles con.|  
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=fullName>|Algunos elementos y clases han experimentado cambios de nombre y se han quitado algunos en WIF 4,5; por ejemplo `Microsoft.IdentityModel.Configuraiton.ServiceConfiguration` es ahora <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Protocols.WSIdentity`|No implementado en WIF 4,5|En WIF 3,5 contiene clases para admitir CardSpace, no implementado en WIF 4,5.|  
|`Microsoft.IdentityModel.Protocols.WSTrust`|División entre <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> y espacios de nombres de <xref:System.ServiceModel.Security?displayProperty=fullName> .|Las clases que representa los artefactos de la WS\- Confianza están en el espacio de nombres de <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName> ; por ejemplo, la clase de <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken> .  Las clases que representan contratos de servicio WCF, se mantiene los host, y los canales que permiten a un servicio WCF para comunicarse mediante el protocolo de la WS\- Confianza están en el espacio de nombres de <xref:System.ServiceModel.Security?displayProperty=fullName> ; por ejemplo, la clase de <xref:System.ServiceModel.Security.WSTrustServiceHost> .|  
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|No implementado en WIF 4,5|\-|  
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|No implementado en WIF 4,5|Clases contenidas que representan constantes de cifrado XML en WIF 3,5.  Estas constantes no se implementan en WIF 4,5.|  
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=fullName>|La clase y las clases de `EnvelopingSignature` que representan constantes no se implementan.|  
|`Microsoft.IdentityModel.SecurityTokenService`|División entre <xref:System.IdentityModel?displayProperty=fullName>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>, y los espacios de nombres de <xref:System.IdentityModel.Tokens?displayProperty=fullName> .|\-|  
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=fullName>|\-|  
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>|Las clases que proporcionan la configuración para escenarios pasivas \(de la WS\- Federación\) se han movido en gran medida a <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>; sin embargo, algunas de estas clases están en <xref:System.IdentityModel.Services?displayProperty=fullName>.|  
|`Microsoft.IdentityModel.Web.Controls`|No implementado en WIF 4,5|Las clases de `Microsoft.IdentityModel.Web.Controls` implementaron el Federated Pasivo Signo\- En el Control, que no existe en WIF 4,5.|  
|`Microsoft.IdentityModel.WindowsTokenService`|No implementado en WIF 4,5|\-|  
  
## Vea también  
 [Novedades de Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)   
 [Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)