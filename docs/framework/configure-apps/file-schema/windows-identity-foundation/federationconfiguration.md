---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: bcd8e00b770517e3faff011b4acee08ebdc5a0df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152741"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> y el (SAM) cuando se usa la autenticación federada a través del protocolo WS-Federation. Configura cuando <xref:System.Security.Claims.ClaimsAuthorizationManager> se <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la clase o la para proporcionar control de acceso basado en notificaciones.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<federationConfiguration>**  
  
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
|name|El nombre único de este elemento de configuración de federación. Este atributo proporciona principalmente un punto de extensibilidad para protocolos futuros. Opcional.|  
|identityConfigurationName|El nombre de la sección de [ \<](identityconfiguration.md) configuración de identidad tal como se especifica en un elemento de>identityConfiguration que se va a utilizar. Si no se especifica este atributo, se utiliza la sección de configuración de identidad predeterminada. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<>de cookieHandler](cookiehandler.md)|Configura el controlador de cookies utilizado por el SAM. Opcional.|  
|[\<serviceCertificate>](servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar tokens. Opcional.|  
|[\<wsFederation>](wsfederation.md)|Configura el módulo de autenticación WS-Federation (WSFAM). Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sección de configuración para la autenticación mediante el protocolo WS-Federation.|  
  
## <a name="remarks"></a>Observaciones  
 El \<elemento de> federationConfiguration proporciona la configuración en dos escenarios diferentes:  
  
- Cuando se usa WS-Federation en una aplicación web <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> pasiva, el elemento contiene <xref:System.IdentityModel.Services.SessionAuthenticationModule> valores que configuran (WSFAM) y (SAM). También hace referencia a la configuración de identidad que se usará para configurar controladores y certificados de tokens de seguridad y componentes como el administrador de autorización de notificaciones y el administrador de autenticación de notificaciones.  
  
- Cuando se <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la clase o la para proporcionar control de acceso basado en notificaciones en el código, el elemento hace referencia a la configuración de identidad que configura el administrador de autorización de notificaciones y la directiva que se usa para tomar decisiones de autorización. Esto es cierto, incluso en escenarios que no son escenarios Web pasivos; por ejemplo, aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación web pasiva, el `<federationConfiguration>` [ \<elemento claimsAuthorizationManager>](claimsauthorizationmanager.md) (y sus elementos de directiva secundarios, si están presentes) de la configuración de identidad a la que hace referencia el elemento son la única configuración aplicada. El resto se pasa por alto.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración de federación predeterminada. El comportamiento se define de la siguiente manera:  
  
1. Si no `<federationConfiguration>` hay ningún elemento presente, el tiempo de ejecución crea una configuración de federación y la rellena con valores predeterminados. Esta configuración de federación predeterminada hará referencia a la configuración de identidad predeterminada.  
  
2. Si hay `<federationConfiguration>` un único elemento, es la configuración de federación predeterminada, independientemente de si tiene nombre o no. Si `identityConfiguration` se especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
3. Si hay `<federationConfiguration>` un elemento sin nombre, es la configuración de federación predeterminada. Si `identityConfiguration` se especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
4. Si hay `<federationConfiguration>` varios elementos con `<federationConfiguration>` nombre y no hay ningún elemento sin nombre, se produce una excepción.  
  
 Normalmente, solo `<federationConfiguration>` se define una sola sección. Esta sección es la configuración de federación predeterminada. Puede especificar varios elementos `<federationConfiguration>` con un nombre único; sin embargo, en este caso, si desea cargar una configuración de federación que no sea la sin nombre, debe proporcionar un controlador para el. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>evento y <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> establezca la propiedad <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> dentro del controlador en `<federationConfiguration>` un objeto inicializado con valores del elemento adecuado en el archivo de configuración.  
  
 El `<federationConfiguration>` elemento se representa <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> mediante la clase. El propio objeto de configuración <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> está representado por la clase. Una <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> única instancia se <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> establece en la propiedad y proporciona una configuración federada para la aplicación.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML `<federationConfiguration>` muestra un elemento que especifica la configuración de WSFAM y <xref:System.IdentityModel.Services.ChunkedCookieHandler> especifica que el SAM utilizará el controlador de cookies predeterminado (una instancia de la clase).  
  
> [!WARNING]
> En este ejemplo, ni el controlador de cookies ni WSFAM son necesarios para usar HTTPS. Esto se `requireHttps` debe a `<wsFederation>` que `requireSsl` el atributo `<cookieHandlerElement>` `false`del elemento y el atributo en el are . Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden suponer un riesgo para la seguridad.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
