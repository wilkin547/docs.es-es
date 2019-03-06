---
title: Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5
ms.date: 03/30/2017
ms.assetid: a092d98c-444d-4336-a644-63c2e11e96c8
author: BrucePerlerMS
ms.openlocfilehash: ef5801ccfdda22b1c89c22ea9c2b14ea0855ed26
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352794"
---
# <a name="namespace-mapping-between-wif-35-and-wif-45"></a>Asignación de espacio de nombres entre WIF 3.5 y WIF 4.5

A partir de .NET 4.5, Windows Identity Foundation (WIF) se ha integrado por completo en .NET Framework. Esta integración ha dado lugar a cambios en los nombres y a la consolidación de los espacios de nombres y la superficie de la API de WIF. En este tema se proporcionan directrices y una asignación general entre los espacios de nombres de WIF 3.5 y los espacios de nombres de WIF 4.5. No pretende ser exhaustivo, sino proporcionar información general sobre dónde encontrar las clases conocidas de WIF 3.5 en WIF 4.5. Para obtener más información sobre las diferencias entre WIF 3.5 y WIF 4.5, vea [What's New in Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md) (Novedades de Windows Identity Foundation 4.5). Para obtener instrucciones sobre cómo migrar a WIF 4.5 una aplicación compilada con WIF 3.5, vea [Guidelines for Migrating an Application Built Using WIF 3.5 to WIF 4.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md) (Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5).

## <a name="wif-35-to-wif-45-namespace-map"></a>Asignación de espacios de nombres de WIF 3.5 a WIF 4.5

Las clases WIF, que se recopilaban en los espacios de nombres `Microsoft.IdentityModel` en WIF 3.5, ahora se distribuyen entre los espacios de nombres siguientes en WIF 4.5: `System.Security.Claims`, `System.ServiceModel.Security` y `System.IdentityModel`. Además, algunos espacios de nombres de WIF 3.5 se han consolidado o se han quitado por completo de WIF 4.5.

> [!IMPORTANT]
> Los siguientes espacios de nombres `System.IdentityModel` contienen clases que implementan el modelo de identidad basado en notificaciones de WCF: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType> y <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>. El modelo de identidad basado en notificaciones de WCF se reemplaza por WIF. No debe utilizar clases en estos tres espacios de nombres cuando compile soluciones basadas en WIF.

En la tabla siguiente se proporciona información sobre dónde se pueden encontrar en WIF 4.5 las clases de WIF 3.5.

|**Espacio de nombres de WIF 3.5**|**Espacio de nombres de WIF 4.5**|**Comentarios**|
|-|-|-|
|`Microsoft.IdentityModel`|<xref:System.IdentityModel?displayProperty=nameWithType>|- La mayoría de las clases que representan constantes no se implementan.<br />- Las clases que se usan para compilar servicios de tokens de seguridad se han movido de `Microsoft.IdentityModel.SecurityTokenService` a <xref:System.IdentityModel?displayProperty=nameWithType>.<br />- Las clases de `Microsoft.IdentityModel.Threading` se han movido a <xref:System.IdentityModel?displayProperty=nameWithType>.<br />- Las clases `ExceptionMapper` y `MruSecurityTokenCache` no se implementan.|
|`Microsoft.IdentityModel.Claims`|<xref:System.Security.Claims?displayProperty=nameWithType>|- Las interfaces `IClaimsPrincipal` y `IClaimsIdentity` no se implementan en WIF 4.5. En su lugar, <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> y <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> son ahora las clases base de las que deriva la mayoría de clases de entidad de seguridad y de identidad de .NET. Esto significa que no se requieren clases especializadas de entidad de seguridad de notificaciones y de identidad como `Microsoft.IdentityModel.Claims.WindowsClaimsPrincipal` y `Microsoft.IdentityModel.Claims.WindowsClaimsIdentity` en WIF 4.5. Use en su lugar <xref:System.Security.Principal.WindowsPrincipal?displayProperty=nameWithType> y <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>. Lo mismo puede decirse de otras clases especializadas de entidad de seguridad de notificaciones y de identidad que existían en WIF 3.5.<br />- La clase `Microsoft.IdentityModel.Claims.ClaimsCollection` no se implementa en WIF 4.5. En su lugar, las colecciones de notificaciones se exponen como colecciones enumerables de tipo <xref:System.Security.Claims.Claim?displayProperty=nameWithType>.<br />-   <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType> y <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> proporcionan métodos que ahora son totalmente compatibles con LINQ.|
|`Microsoft.IdentityModel.Configuration`|<xref:System.IdentityModel.Configuration?displayProperty=nameWithType>|Algunos elementos y clases han cambiado de nombre y algunos se han eliminado de WIF 4.5; por ejemplo, `Microsoft.IdentityModel.Configuration.ServiceConfiguration` ahora es <xref:System.IdentityModel.Configuration.IdentityConfiguration?displayProperty=nameWithType>.|
|`Microsoft.IdentityModel.Protocols`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSFederation`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSFederation.Metadata`|<xref:System.IdentityModel.Metadata?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Protocols.WSIdentity`|No se implementa en WIF 4.5.|En WIF 3.5 contenía clases para admitir CardSpace, pero no se implementa en WIF 4.5.|
|`Microsoft.IdentityModel.Protocols.WSTrust`|Se divide entre los espacios de nombres <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType> y <xref:System.ServiceModel.Security?displayProperty=nameWithType>.|Las clases que representan artefactos de WS-Trust se encuentran en el espacio de nombres <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>; por ejemplo, la clase <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>. Las clases que representan contratos de servicio de WCF, hosts de servicio y canales que permiten que un servicio WCF se comunique a través del protocolo WS-Trust se encuentran en el espacio de nombres <xref:System.ServiceModel.Security?displayProperty=nameWithType>; por ejemplo, la clase <xref:System.ServiceModel.Security.WSTrustServiceHost>.|
|`Microsoft.IdentityModel.Protocols.WSTrust.Bindings`|No se implementa en WIF 4.5.|-|
|`Microsoft.IdentityModel.Protocols.XmlEncryption`|No se implementa en WIF 4.5.|Contenía clases que representan las constantes de cifrado XML en WIF 3.5. Estas constantes no se implementan en WIF 4.5.|
|`Microsoft.IdentityModel.Protocols.XmlSignature`|<xref:System.IdentityModel?displayProperty=nameWithType>|La clase `EnvelopingSignature` y las clases que representan constantes no se implementan.|
|`Microsoft.IdentityModel.SecurityTokenService`|Se divide entre los espacios de nombres <xref:System.IdentityModel?displayProperty=nameWithType>, <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType> y <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>.|-|
|`Microsoft.IdentityModel.Threading`|<xref:System.IdentityModel?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens.Saml11`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Tokens.Saml2`|<xref:System.IdentityModel.Tokens?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Web`|<xref:System.IdentityModel.Services?displayProperty=nameWithType>|-|
|`Microsoft.IdentityModel.Web.Configuration`|<xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>|Las clases que proporcionan configuración para escenarios pasivos (WS-Federation) se han trasladado en gran medida a <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>, pero algunas de estas clases se encuentran en <xref:System.IdentityModel.Services?displayProperty=nameWithType>.|
|`Microsoft.IdentityModel.Web.Controls`|No se implementa en WIF 4.5.|Las clases en `Microsoft.IdentityModel.Web.Controls` implementaban el control de inicio de sesión pasivo federado, que no existe en WIF 4.5.|
|`Microsoft.IdentityModel.WindowsTokenService`|No se implementa en WIF 4.5.|-|

## <a name="see-also"></a>Vea también

- [Novedades de Windows Identity Foundation 4.5](../../../docs/framework/security/whats-new-in-wif.md)
- [Directrices para migrar a WIF 4.5 una aplicación compilada con WIF 3.5](../../../docs/framework/security/guidelines-for-migrating-an-application-built-using-wif-3-5-to-wif-4-5.md)
