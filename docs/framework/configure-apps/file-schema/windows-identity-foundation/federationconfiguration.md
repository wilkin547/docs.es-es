---
description: 'Más información acerca de: <federationConfiguration>'
title: <federationConfiguration>
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
ms.openlocfilehash: f8793a8fbd6fc6d5e6994c8e368f587b740e5973
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748991"
---
# \<federationConfiguration>

Configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) cuando se usa la autenticación federada a través del protocolo de WS-Federation. Configura <xref:System.Security.Claims.ClaimsAuthorizationManager> cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar el control de acceso basado en notificaciones.  
  
[**\<configuration>**](../configuration-element.md)\
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
|name|El nombre único de este elemento de configuración de federación. Este atributo proporciona principalmente un punto de extensibilidad para los protocolos futuros. Opcional.|  
|identityConfigurationName|Nombre de la sección de configuración de identidad tal y como se especifica en un [\<identityConfiguration>](identityconfiguration.md) elemento que se va a usar. Si no se especifica este atributo, se usa la sección de configuración de identidad predeterminada. Opcional.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configura el controlador de cookies que usa el SAM. Opcional.|  
|[\<serviceCertificate>](servicecertificate.md)|Configura el certificado que se usa para cifrar y descifrar los tokens. Opcional.|  
|[\<wsFederation>](wsfederation.md)|Configura el módulo de autenticación de WS-Federation (WSFAM). Opcional.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<system.identityModel.services>](system-identitymodel-services.md)|Sección de configuración para la autenticación mediante el protocolo WS-Federation.|  
  
## <a name="remarks"></a>Observaciones  

 El \<federationConfiguration> elemento proporciona valores en dos escenarios diferentes:  
  
- Al usar WS-Federation en una aplicación web pasiva, el elemento contiene opciones de configuración que configuran <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). También hace referencia a la configuración de identidad que se va a usar para configurar los controladores y certificados de tokens de seguridad, así como a los componentes como el administrador de autorización de notificaciones y el administrador de autenticación de notificaciones.  
  
- Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el elemento hace referencia a la configuración de identidad que configura el administrador de autorización de notificaciones y la Directiva que se usa para tomar decisiones de autorización. Esto es cierto, incluso en escenarios que no son escenarios web pasivos; por ejemplo, aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación web pasiva, el [\<claimsAuthorizationManager>](claimsauthorizationmanager.md) elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que hace referencia el `<federationConfiguration>` elemento, son los únicos valores aplicados. El resto se pasa por alto.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración de Federación predeterminada. El comportamiento se define de la siguiente manera:  
  
1. Si no hay ningún `<federationConfiguration>` elemento presente, el tiempo de ejecución crea una configuración de Federación y la rellena con los valores predeterminados. Esta configuración de Federación predeterminada hará referencia a la configuración de identidad predeterminada.  
  
2. Si hay un único `<federationConfiguration>` elemento, es la configuración predeterminada de la Federación independientemente de si tiene nombre o no. Si `identityConfiguration` se especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
3. Si hay un elemento sin nombre `<federationConfiguration>` , es la configuración predeterminada de la Federación. Si `identityConfiguration` se especifica su atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de identidad predeterminada.  
  
4. Si hay varios `<federationConfiguration>` elementos con nombre presentes y no hay ningún `<federationConfiguration>` elemento sin nombre, se produce una excepción.  
  
 Normalmente, solo `<federationConfiguration>` se define una sección. Esta sección es la configuración de Federación predeterminada. Puede especificar varios elementos con el nombre único `<federationConfiguration>` ; sin embargo, en este caso, si desea cargar una configuración de Federación distinta de la sin nombre, debe proporcionar un controlador para. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> y establezca la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> propiedad dentro del controlador en un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto inicializado con los valores del elemento adecuado `<federationConfiguration>` en el archivo de configuración.  
  
 El `<federationConfiguration>` elemento se representa mediante la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> clase. La clase representa el propio objeto de configuración <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> . <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>Se establece una sola instancia en la <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> propiedad y se proporciona la configuración federada para la aplicación.  
  
## <a name="example"></a>Ejemplo  

 En el XML siguiente se muestra un `<federationConfiguration>` elemento que especifica los valores para WSFAM y especifica que el SAM debe usar el controlador de cookies predeterminado (una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase).  
  
> [!WARNING]
> En este ejemplo, ni el controlador de cookies ni WSFAM son necesarios para usar HTTPS. Esto se debe a que el `requireHttps` atributo del `<wsFederation>` elemento y el `requireSsl` atributo de `<cookieHandlerElement>` son `false` . Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden suponer un riesgo para la seguridad.  
  
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
