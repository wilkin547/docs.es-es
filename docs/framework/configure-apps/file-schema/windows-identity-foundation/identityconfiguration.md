---
title: <identityConfiguration>
ms.date: 03/30/2017
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
author: BrucePerlerMS
ms.openlocfilehash: 0fa8c574fd5663606cf081f1000a24884306edfe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251993"
---
# \<identityConfiguration>

Especifica la configuración de identidad de nivel de servicio.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<identityConfiguration>**  

## <a name="syntax"></a>Sintaxis

```xml
<system.identityModel>
  <identityConfiguration
      name=xs:string
      saveBootstrapContext=xs:boolean>
      maximumClockSkew=TimeSpan >
  </identityConfiguration>
</system.identityModel>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|name|Nombre de la sección de configuración de identidad. Puede usar este nombre para hacer referencia a una sección de configuración específica. Si no `name` se especifica ningún atributo, en la sección se define la configuración predeterminada. La configuración predeterminada siempre se utiliza para escenarios de Federación pasiva. Para obtener más información, vea el [\<federationConfiguration>](federationconfiguration.md) elemento.|
|saveBootstrapContext|Especifica si los tokens de arranque deben incluirse en el token de sesión. El valor también se puede establecer en una colección de controladores de tokens estableciendo el `saveBootstrapContext` atributo en el [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento. Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.|
|maximumClockSkew|<xref:System.TimeSpan>Que especifica el sesgo de reloj máximo permitido. Controla el sesgo de reloj máximo permitido al realizar operaciones dependientes del tiempo, como la validación de la hora de expiración de una sesión de inicio de sesión. El valor predeterminado es 5 minutos, "00:05:00". Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, vea [valores TimeSpan](../windows-workflow-foundation/index.md). El sesgo de reloj máximo también se puede establecer en una colección de controladores de tokens estableciendo el `maximumClockSkew` atributo en el [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento. Un valor establecido en la colección de controladores de tokens invalida el valor establecido en el servicio.|

### <a name="child-elements"></a>Elementos secundarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<caches>](caches.md)|Registra las cachés utilizadas para los tokens de sesión y la detección de reproducción de tokens. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Opcional.|
|[\<certificateValidation>](certificatevalidation.md)|Controla la configuración que usan los controladores de token para validar certificados. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Opcional.|
|[\<claimsAuthenticationManager>](claimsauthenticationmanager.md)|Registra un administrador de autenticación de notificaciones para las notificaciones entrantes. Opcional.|
|[\<claimsAuthorizationManager>](claimsauthorizationmanager.md)|Registra un administrador de autorización de notificaciones para las notificaciones entrantes. Opcional.|
|[\<claimTypeRequired>](claimtyperequired.md)|Especifica el conjunto de notificaciones necesarias para los tokens de seguridad de entrada. Opcional.|
|[\<securityTokenHandlers>](securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad. Se pueden especificar cero o más colecciones de controladores de token de seguridad. Opcional.|
|[\<tokenReplayDetection>](tokenreplaydetection.md)|Habilita la detección de reproducción de tokens y especifica la hora de expiración de los tokens. Se puede especificar en el nivel de servicio o en una colección de controladores de tokens de seguridad. Opcional.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<system.identityModel>](system-identitymodel.md)|Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.|

## <a name="remarks"></a>Comentarios

Se pueden definir varias configuraciones de identidad, cada una con un nombre único. El comportamiento es el siguiente:

1. Si no `<identityConfiguration>` se especifica ningún elemento. Una configuración de identidad predeterminada se crea en tiempo de ejecución y se rellena con los valores predeterminados.

2. Si `<identityConfiguration>` se especifica un solo elemento. Es la configuración de identidad predeterminada. No importa si tiene nombre o sin nombre.

3. Si `<identityConfiguration>` se especifican varios elementos. El elemento sin nombre especifica la configuración de identidad predeterminada. Se recomienda que, cuando se especifican varios `<identityConfiguration>` elementos, uno de ellos no tenga nombre.

> [!WARNING]
> Si se especifican varios `<identityConfiguration>` elementos, uno de ellos debe tener el mismo nombre. El elemento sin nombre será la configuración de identidad predeterminada.

 Algunas de las opciones especificadas en el `<identityConfiguration>` elemento se pueden invalidar con la configuración de una colección de controladores de tokens de seguridad o con la configuración de los controladores de token de seguridad individuales.

> [!IMPORTANT]
> Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que hace referencia el `<federationConfiguration>` elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para tomar decisiones de autorización. Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación web pasiva, el [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados. Todos los demás valores no se tienen en cuenta. Para obtener más información, vea el [\<federationConfiguration>](federationconfiguration.md) elemento.

El `<identityConfiguration>` elemento se representa mediante la <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> clase. La clase representa una sección de configuración de identidad <xref:System.IdentityModel.Configuration.IdentityConfiguration> .

> [!IMPORTANT]
> La especificación de los siguientes elementos como elementos secundarios del `<identityConfiguration>` elemento está en desuso, aunque el comportamiento todavía se admite por compatibilidad con versiones anteriores. En su lugar, estos elementos deben especificarse en el [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) elemento.
>
> - [\<audienceUris>](audienceuris.md)
> - [\<issuerNameRegistry>](issuernameregistry.md)
> - [\<issuerTokenResolver>](issuertokenresolver.md)
> - [\<serviceTokenResolver>](servicetokenresolver.md)

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crea una configuración de identidad denominada "alternateConfiguration". La configuración de identidad especifica la configuración predeterminada.

```xml
<system.identityModel>
    <identityConfiguration name="alternateConfiguration"/>
</system.identityModel>
```

## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Configuration.IdentityConfiguration>
- <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
