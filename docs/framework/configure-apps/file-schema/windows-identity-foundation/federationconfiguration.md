---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 44014d620dcd03e055eb58b50a1428b8e1b41186
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) al usar federado autenticación a través del protocolo WS-Federation. Configura el <xref:System.Security.Claims.ClaimsAuthorizationManager> cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar el control de acceso basado en notificaciones.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|name|El nombre de este elemento de configuración de federación. Principalmente, este atributo proporciona un punto de extensibilidad para protocolos futuros. Opcional.|  
|identityConfigurationName|El nombre de la sección de configuración de identidad como se especifica en un [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento que se va a usar. Si no se especifica este atributo, se usa la sección de configuración de la identidad de forma predeterminada. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el controlador de cookie utilizado por el SAM. Opcional.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se utiliza para cifrar y descifrar los tokens. Opcional.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Configura el módulo de autenticación de WS-Federation (WSFAM). Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Sección de configuración para la autenticación mediante el protocolo WS-Federation.|  
  
## <a name="remarks"></a>Comentarios  
 El \<federationConfiguration > elemento proporciona opciones de configuración en dos escenarios diferentes:  
  
-   Cuando se usa WS-Federation en una aplicación Web pasiva, el elemento contiene ajustes que configuren el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). También hace referencia a la configuración de identidad que se usará para configurar controladores de tokens de seguridad y los componentes como el Administrador de autorización de notificaciones y el Administrador de autenticación de notificaciones y los certificados.  
  
-   Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> de clases para proporcionar control de acceso basado en notificaciones en el código, el elemento hace referencia a la configuración de identidad que configura el Administrador de autorización de notificaciones y la directiva que se utiliza para realizar la autorización decisiones. Esto es así, incluso en escenarios que no son escenarios Web pasivos; Por ejemplo, las aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no esté basado en Web. Si la aplicación no es una aplicación Web pasiva, el [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) element (y sus elementos de directiva secundarios, si está presente) de la configuración de identidad al que hace referencia el `<federationConfiguration>` elemento se aplican las únicas opciones. El resto se pasa por alto.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración de la federación de forma predeterminada. El comportamiento se define como sigue:  
  
1.  Si no hay ningún `<federationConfiguration>` elemento está presente, el tiempo de ejecución crea una configuración de federación y lo rellena con valores predeterminados. Esta configuración de federación predeterminada hará referencia a la configuración de la identidad predeterminada.  
  
2.  Si una sola `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación independientemente de si se denomina o sin nombre. Si su `identityConfiguration` se especifica el atributo, se hace referencia a la configuración de identidad con nombre; en caso contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
3.  Si una sin nombre `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación. Si su `identityConfiguration` se especifica el atributo, se hace referencia a la configuración de identidad con nombre; en caso contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
4.  Si varios denominado `<federationConfiguration>` elementos están presentes y sin nombre no `<federationConfiguration>` elemento está presente, se produce una excepción.  
  
 Por lo general, solo una `<federationConfiguration>` se define la sección. Esta sección es la configuración de federación de forma predeterminada. Puede especificar varios, denominado de forma única `<federationConfiguration>` elementos; sin embargo, en este caso, si desea cargar una configuración de federación que no sea el sin nombre, debe proporcionar un controlador para el. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> eventos y establezca la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> propiedad dentro del controlador para una <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto inicializado con los valores con la correspondiente `<federationConfiguration>` elemento en el archivo de configuración.  
  
 El `<federationConfiguration>` elemento representado por la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> clase. El propio objeto de configuración se representa mediante la <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> clase. Una sola <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instancia se establece en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y proporciona una configuración federada para la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra un `<federationConfiguration>` elemento que especifica valores para el WSFAM y especifica que el controlador de cookies predeterminado (una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase) se usa el SAM.  
  
> [!WARNING]
>  En este ejemplo, el controlador de cookies ni WSFAM se requieren para usar HTTPS. Esto es porque el `requireHttps` del atributo en el `<wsFederation>` elemento y el `requireSsl` del atributo en el `<cookieHandlerElement>` son `false`. Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden presentar un riesgo de seguridad.  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation passiveRedirectEnabled="true"   
      issuer="http://localhost:15839/wsFederationSTS/Issue"   
      realm="http://localhost:50969/" reply="http://localhost:50969/"   
      requireHttps="false"   
      signOutReply="http://localhost:50969/SignedOutPage.html"   
      signOutQueryString="Param1=value2&Param2=value2"   
      persistentCookiesOnPassiveRedirects="true" />  
    <cookieHandler requireSsl="false" />  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
