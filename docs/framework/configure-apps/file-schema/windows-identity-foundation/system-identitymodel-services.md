---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
Sección de configuración para la autenticación mediante el protocolo WS-Federation.  
  
 \<system.identityModel.services >  
  
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
 Ninguna  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene los valores que configuran la <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) y la <xref:System.IdentityModel.Services.SessionAuthenticationModule> módulos HTTP de (seguridad SAM).|  
  
### <a name="parent-elements"></a>Elementos primarios  
 Ninguna  
  
## <a name="remarks"></a>Comentarios  
 Agregar un `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración para el SAM y WSFAM.  
  
> [!IMPORTANT]
>  Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar el control de acceso basado en notificaciones en el código, el Administrador de autorización de notificaciones (<xref:System.Security.Claims.ClaimsAuthorizationManager>) y la directiva que se utiliza para tomar decisiones de autorización se configuran a través de un `<identityConfiguration>` elemento que hace referencia implícita o explícitamente desde un `<federationConfiguration>` elemento de esta sección. Para obtener más información, consulte el **comentarios** en el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 El `<system.identityModel.services>` sección está representada por la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase. La colección del elemento secundario `<federationConfiguration>` elementos configurados en la sección está representado por la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código XML muestra cómo agregar un `<system.identityModel.services>` sección a un archivo de configuración. Primero debe agregar las declaraciones de sección tanto para el `<system.identityModel.services>` sección y `<system.identityModel>` secciones. (Cuando se agrega un `<system.identityModel.services>` sección, también debe agregar una declaración para el `<system.identityModel>` sección para asegurarse de que un valor predeterminado `<identityConfiguration>` sección puede crearse en tiempo de ejecución si es necesario.) Una vez agregadas las declaraciones de sección, puede configurar opciones de autenticación federada en el `<system.identityModel.services>` elemento.  
  
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
