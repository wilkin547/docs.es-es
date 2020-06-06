---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152509"
---
# \<system.identityModel.services>
Sección de configuración para la autenticación mediante el protocolo WS-Federation.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<system.identityModel.services>**  
  
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
 None  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene la configuración que configura los <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> módulos http (WSFAM) y <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
### <a name="parent-elements"></a>Elementos primarios  
 None  
  
## <a name="remarks"></a>Observaciones  
 Agregue una `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración de Sam y WSFAM.  
  
> [!IMPORTANT]
> Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el administrador de autorización de notificaciones ( <xref:System.Security.Claims.ClaimsAuthorizationManager> ) y la Directiva que se usa para tomar decisiones de autorización se configuran mediante un `<identityConfiguration>` elemento al que se hace referencia de forma implícita o explícita desde un `<federationConfiguration>` elemento de esta sección. Para obtener más información, vea las **notas** del [\<federationConfiguration>](federationconfiguration.md) elemento.  
  
 La `<system.identityModel.services>` sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase. La colección de `<federationConfiguration>` elementos secundarios configurada en la sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo agregar una `<system.identityModel.services>` sección a un archivo de configuración. Primero debe agregar declaraciones de sección para la `<system.identityModel.services>` sección y las `<system.identityModel>` secciones. (Al agregar una `<system.identityModel.services>` sección, también debe agregar una declaración para la `<system.identityModel>` sección para asegurarse de que `<identityConfiguration>` el tiempo de ejecución puede crear una sección predeterminada, si es necesario). Una vez agregadas las declaraciones de sección, puede configurar las opciones de autenticación federada en el `<system.identityModel.services>` elemento.  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
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
  
</configuration>  
```
