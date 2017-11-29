---
title: '&lt;identityConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b1cca286fc967631c60aa02a1318fe24120e05b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
Especifica los valores de identidad de nivel de servicio.  
  
 \<system.identityModel >  
\<identityConfiguration >  
  
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
|name|El nombre de la sección de configuración de identidad. Puede utilizar este nombre para hacer referencia a una sección de configuración específico. Si no hay ningún `name` atributo se especifica, la configuración predeterminada define en la sección. La configuración predeterminada siempre se utiliza para escenarios de federación pasiva. Para obtener más información, consulte el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.|  
|saveBootstrapContext|Especifica si los tokens de arranque deben incluirse en el token de sesión. El valor también puede establecerse en una colección de controlador de token estableciendo la `saveBootstrapContext` del atributo en el [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.|  
|maximumClockSkew|Un <xref:System.TimeSpan> que define el sesgo de reloj permitido máximo. Controla el sesgo de reloj permitido máximo al realizar operaciones de sujetos a limitación temporal, como la validación de la fecha de expiración de una sesión de inicio de sesión. El valor predeterminado es 5 minutos, "00: 05:00". Para obtener más información sobre cómo especificar <xref:System.TimeSpan> valores, consulte [valores de intervalo de tiempo](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md). El sesgo de reloj máximo también puede establecerse en una colección de controlador de token estableciendo la `maximumClockSkew` del atributo en el [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento. Un valor establecido en la colección de controlador de token reemplaza al valor establecido en el servicio.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<almacena en memoria caché >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|Registra las memorias caché que se utiliza para la detección de reproducción de tokens y símbolos de sesión. Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Opcional.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|Controla la configuración que usan los controladores de tokens para validar certificados. Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Opcional.|  
|[\<claimsAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|Registra un administrador de autenticación de notificaciones para las notificaciones entrantes. Opcional.|  
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|Registra un administrador de autorización de notificaciones para las notificaciones entrantes. Opcional.|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|Especifica el conjunto de notificaciones necesarias para los tokens de seguridad entrantes. Opcional.|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|Especifica una colección de controladores de tokens de seguridad. Se pueden especificar cero o más colecciones de controladores de tokens de seguridad. Opcional.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|Habilita la detección de reproducción de tokens y especifica la hora de expiración de símbolos (tokens). Puede especificarse en el nivel de servicio o en una colección de controlador de token de seguridad. Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|Proporciona la configuración para habilitar las opciones de Windows Identity Foundation (WIF) en las aplicaciones.|  
  
## <a name="remarks"></a>Comentarios  
 Varias identidades es posible definir configuraciones, cada uno con un nombre único. El comportamiento es como sigue:  
  
1.  Si no hay ningún `<identityConfiguration>` se especifica. Una configuración de la identidad predeterminada se crea en tiempo de ejecución y se rellena con valores predeterminados.  
  
2.  Si una sola `<identityConfiguration>` se especifica. Es la configuración predeterminada de la identidad. No importa, con nombre o sin nombre.  
  
3.  Si hay varios `<identityConfiguration>` elementos se especifican. El elemento sin nombre especifica la configuración de la identidad predeterminada. Se recomienda que al especificar varios `<identityConfiguration>` elementos, uno de ellos debe ser sin nombre.  
  
> [!WARNING]
>  Si especifica varios `<identityConfiguration>` elementos, uno de ellos debe ser sin nombre. El elemento sin nombre será la configuración de la identidad predeterminada.  
  
 Algunos de los valores especificados en la `<identityConfiguration>` elemento puede reemplazarse por la configuración en una colección de controlador de token de seguridad o la configuración de controladores de tokens de seguridad individuales.  
  
> [!IMPORTANT]
>  Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar el control de acceso basado en notificaciones en el código, la configuración de identidad que hace referencia el `<federationConfiguration>` elemento configura el Administrador de autorización de notificaciones y la directiva que se utiliza para realizar decisiones de autorización. Esto es cierto incluso en escenarios que no son escenarios pasivos de Web, por ejemplo, las aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no esté basado en Web. Si la aplicación no es una aplicación Web pasiva, el [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (y sus elementos de directiva secundarios, si está presente) de la configuración de identidad que se hace referencia son los únicos valores que se aplican. Se omiten todas las demás opciones. Para obtener más información, consulte el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 El `<identityConfiguration>` elemento representado por la <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> clase. Una sección de configuración de identidad está representada por la <xref:System.IdentityModel.Configuration.IdentityConfiguration> clase.  
  
> [!IMPORTANT]
>  Especificar los siguientes elementos como elementos secundarios de la `<identityConfiguration>` elemento está en desuso, aunque el comportamiento todavía se admite por compatibilidad con versiones anteriores. Estos elementos en su lugar, deben especificarse en el [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) elemento.  
>   
>  -   [\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una configuración de identidad con el nombre "alternateConfiguration". La configuración de identidad especifica la configuración predeterminada.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
