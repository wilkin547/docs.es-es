---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 66fa16992d779b08ee8c55598efc98f8f5267656
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847807"
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
Configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) cuando se usa federados de autenticación a través del protocolo WS-Federation. Configura el <xref:System.Security.Claims.ClaimsAuthorizationManager> cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar control de acceso basado en notificaciones.  
  
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
|identityConfigurationName|El nombre de la sección de configuración de identidad como se especifica en un [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento va a usar. Si no se especifica este atributo, se usa la sección de configuración de identidad predeterminada. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|Configura el controlador de cookies que usa SAM. Opcional.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar los tokens. Opcional.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Configura el módulo de autenticación de WS-Federation (WSFAM). Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Sección de configuración para la autenticación mediante el protocolo WS-Federation.|  
  
## <a name="remarks"></a>Comentarios  
 El \<federationConfiguration > elemento proporciona configuraciones en dos escenarios diferentes:  
  
-   Cuando se utiliza WS-Federation en una aplicación Web pasiva, el elemento contiene los valores que configuren el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y la <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). También hace referencia a la configuración de identidad que se usará para configurar los controladores de token de seguridad y certificados y los componentes como el Administrador de autorización de notificaciones y el Administrador de autenticación de notificaciones.  
  
-   Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> para proporcionar control de acceso basado en notificaciones en el código de clase, el elemento hace referencia a la configuración de identidad que configura el Administrador de autorización de notificaciones y la directiva que se utiliza para realizar la autorización decisiones. Esto es cierto incluso en escenarios que no son escenarios pasivos de Web; Por ejemplo, las aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación Web pasiva, el [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento (y sus elementos secundarios de directiva, si está presente) de la configuración de identidad al que hace referencia el `<federationConfiguration>` elemento ¿se aplica la configuración única. El resto se pasa por alto.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración de federación de forma predeterminada. El comportamiento se define como sigue:  
  
1.  Si no hay ningún `<federationConfiguration>` elemento está presente, el tiempo de ejecución crea una configuración de federación y rellenarla con los valores predeterminados. Esta configuración de federación predeterminada hará referencia a la configuración de la identidad predeterminada.  
  
2.  Si una sola `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación independientemente de si se denominado o sin nombre. Si su `identityConfiguration` atributo se especifica, se hace referencia a la configuración de identidad con nombre; en caso contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
3.  Si una sin nombre `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación. Si su `identityConfiguration` atributo se especifica, se hace referencia a la configuración de identidad con nombre; en caso contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
4.  Si el nombre de varios `<federationConfiguration>` elementos están presentes y sin nombre no `<federationConfiguration>` elemento está presente, se produce una excepción.  
  
 Normalmente, una sola `<federationConfiguration>` sección se define. En esta sección es la configuración de federación de forma predeterminada. Puede especificar varios, un nombre único `<federationConfiguration>` elementos; sin embargo, en este caso, si desea cargar una configuración de federación que no sea el sin nombre, debe proporcionar un controlador para el. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> evento y establecer el <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> propiedad dentro del controlador para un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto inicializado con los valores con la correspondiente `<federationConfiguration>` elemento en el archivo de configuración.  
  
 El `<federationConfiguration>` elemento representado por la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> clase. El propio objeto de configuración se representa mediante el <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> clase. Una sola <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instancia se establece en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y proporciona una configuración federada para la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra un `<federationConfiguration>` elemento que especifica valores para el WSFAM y especifica que el controlador de cookies predeterminado (una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase) se usa SAM.  
  
> [!WARNING]
>  En este ejemplo, el controlador de cookies ni WSFAM son necesarios para usar HTTPS. Esto es porque el `requireHttps` atributo el `<wsFederation>` elemento y el `requireSsl` atributo el `<cookieHandlerElement>` son `false`. Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden presentar un riesgo de seguridad.  
  
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
