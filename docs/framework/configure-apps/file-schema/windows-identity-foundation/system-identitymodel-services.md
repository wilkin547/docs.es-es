---
title: "&lt;system.identityModel.services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;system.identityModel.services&gt;
Sección de configuración para la autenticación mediante el protocolo WS\-Federation.  
  
 \<system.identityModel.services\>  
  
## Sintaxis  
  
```  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 None  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|Contiene las opciones que configurar el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> módulos HTTP \(SAM\).|  
  
### Elementos primarios  
 None  
  
## Comentarios  
 Agregar una `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar una configuración para el SAM y WSFAM.  
  
> [!IMPORTANT]
>  Cuando se utiliza el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar control de acceso basado en notificaciones en el código, el Administrador de autorización de reclamaciones \(<xref:System.Security.Claims.ClaimsAuthorizationManager>\) y directivas que se utilizan para tomar decisiones de autorización se configuran a través de un `<identityConfiguration>` elemento que hace referencia implícitamente o explícitamente de una `<federationConfiguration>` elemento en esta sección.  Para obtener más información, consulte el  **palabras** en el [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 El `<system.identityModel.services>` sección está representado por el <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase.  La colección de niño `<federationConfiguration>` elementos configurados en la sección está representado por el <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> clase.  
  
## Ejemplo  
 El XML siguiente muestra cómo agregar un `<system.identityModel.services>` sección a un archivo de configuración.  En primer lugar debe agregar las declaraciones de sección tanto para el `<system.identityModel.services>` sección y la `<system.identityModel>` las secciones.  \(Cuando se agrega un `<system.identityModel.services>` sección, también debe agregar una declaración para el `<system.identityModel>` sección para asegurarse de que un valor predeterminado `<identityConfiguration>` sección puede crearse mediante el tiempo de ejecución si es necesario.\) Después de que se han agregado las declaraciones de sección, puede configurar opciones de autenticación federados en virtud de la `<system.identityModel.services>` elemento.  
  
```  
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