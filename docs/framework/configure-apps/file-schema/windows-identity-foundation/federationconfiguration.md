---
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: 148b2f3e12fbfbf85b800f0ca7f5dc7dc1845d24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251999"
---
# <a name="federationconfiguration"></a>\<federationConfiguration>
Configura <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> y (SAM) al usar la autenticación federada a través del protocolo WS-Federation. Configura <xref:System.Security.Claims.ClaimsAuthorizationManager> cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar el control de acceso basado en notificaciones.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. identityModel. Services >** ](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<> federationConfiguration**  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|name|Nombre de este elemento de configuración de Federación. Este atributo proporciona principalmente un punto de extensibilidad para los protocolos futuros. Opcional.|  
|identityConfigurationName|Nombre de la sección de configuración de identidad tal y como [ \<](identityconfiguration.md) se especifica en un elemento de > identityConfiguration que se va a usar. Si no se especifica este atributo, se usa la sección de configuración de identidad predeterminada. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura el controlador de cookies que usa el SAM. Opcional.|  
|[\<serviceCertificate>](servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar los tokens. Opcional.|  
|[\<wsFederation>](wsfederation.md)|Configura el módulo de autenticación de WS-Federation (WSFAM). Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sección de configuración para la autenticación mediante el protocolo WS-Federation.|  
  
## <a name="remarks"></a>Comentarios  
 El \<elemento > federationConfiguration proporciona opciones de configuración en dos escenarios diferentes:  
  
- Al usar WS-Federation en una aplicación web pasiva, el elemento contiene opciones de configuración que <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> configuran (WSFAM <xref:System.IdentityModel.Services.SessionAuthenticationModule> ) y (SAM). También hace referencia a la configuración de identidad que se va a usar para configurar los controladores y certificados de tokens de seguridad, así como a los componentes como el administrador de autorización de notificaciones y el administrador de autenticación de notificaciones.  
  
- Cuando se usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el elemento hace referencia a la configuración de identidad que configura el administrador de autorización de notificaciones y la Directiva que se usa para realizar la autorización. Tome. Esto es cierto, incluso en escenarios que no son escenarios web pasivos; por ejemplo, aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación web pasiva, el [ \<elemento > claimsAuthorizationManager](claimsauthorizationmanager.md) (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la `<federationConfiguration>` que hace referencia el elemento son los únicos valores aplica. El resto se pasa por alto.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración de Federación predeterminada. El comportamiento se define de la siguiente manera:  
  
1. Si no hay ningún `<federationConfiguration>` elemento presente, el tiempo de ejecución crea una configuración de Federación y la rellena con los valores predeterminados. Esta configuración de Federación predeterminada hará referencia a la configuración de identidad predeterminada.  
  
2. Si hay un `<federationConfiguration>` único elemento, es la configuración predeterminada de la Federación independientemente de si tiene nombre o no. Si se `identityConfiguration` especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
3. Si hay un `<federationConfiguration>` elemento sin nombre, es la configuración predeterminada de la Federación. Si se `identityConfiguration` especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
4. Si hay varios `<federationConfiguration>` elementos con nombre presentes y no hay ningún `<federationConfiguration>` elemento sin nombre, se produce una excepción.  
  
 Normalmente, solo se define `<federationConfiguration>` una sección. Esta sección es la configuración de Federación predeterminada. Puede especificar varios elementos con el nombre `<federationConfiguration>` único; sin embargo, en este caso, si desea cargar una configuración de Federación distinta de la sin nombre, debe proporcionar un controlador para. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>y establezca la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> propiedad dentro del controlador en un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto inicializado con los valores del elemento adecuado `<federationConfiguration>` en el archivo de configuración.  
  
 El elemento se representa mediante la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> clase. `<federationConfiguration>` La <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> clase representa el propio objeto de configuración. Se establece <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> una sola instancia en la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y se proporciona la configuración federada para la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el XML siguiente se `<federationConfiguration>` muestra un elemento que especifica los valores para WSFAM y especifica que el SAM debe usar el controlador de <xref:System.IdentityModel.Services.ChunkedCookieHandler> cookies predeterminado (una instancia de la clase).  
  
> [!WARNING]
> En este ejemplo, ni el controlador de cookies ni WSFAM son necesarios para usar HTTPS. Esto se debe `<wsFederation>` a `requireHttps` que el atributo del `<cookieHandlerElement>` elemento y `requireSsl` el atributo de son `false`. Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden suponer un riesgo para la seguridad.  
  
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

- <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>
- <xref:System.IdentityModel.Services.SessionAuthenticationModule>
- <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
- [\<identityConfiguration>](identityconfiguration.md)
