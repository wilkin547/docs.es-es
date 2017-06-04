---
title: "&lt;federationConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;federationConfiguration&gt;
Configura el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) cuando se utiliza federados autenticación a través del protocolo WS\-Federation.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
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
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Atributo  Descripción  Opcional.|  
|name|El nombre de la sección de configuración de identidad como se especifica en un [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) elemento a utilizar.  Si no se especifica este atributo, se utiliza la sección de configuración de identidad predeterminada.  Opcional.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|ruta de acceso  Opcional.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|Configura el certificado que se utiliza para cifrar y descifrar los símbolos \(tokens\).  Opcional.|  
|[\<wsFederation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|Configura el módulo de autenticación de WS\-Federation \(WSFAM\).  Opcional.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|mode|  
  
## Comentarios  
 \<federationConfiguration\> elemento proporciona configuraciones en dos escenarios diferentes:  
  
-   Al utilizar WS\-Federation en una aplicación Web pasiva, el elemento contiene los valores que configure el <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\) y el <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).  También hace referencia a la configuración de identidad que se utilizará para configurar los componentes como el Administrador de autorización de reclamaciones y el Administrador de autenticación de reclamaciones y certificados y los controladores de token de seguridad.  
  
-   Cuando se utiliza el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> para proporcionar control de acceso basado en notificaciones en el código de clase, el elemento hace referencia a la configuración de identidad que configura el Administrador de autorización de reclamaciones y la directiva que se utiliza para tomar decisiones de autorización.  Esto es cierto, incluso en escenarios que no son los escenarios Web pasivos; Por ejemplo, las aplicaciones de Windows Communication Foundation \(WCF\) o una aplicación que no está basado en Web.  Si la aplicación no es una aplicación Web pasiva, el [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) elemento \(y sus elementos de directiva de secundarios, si está presente\) de la configuración de la identidad hace referencia a la `<federationConfiguration>` elemento son los únicos valores que se aplica.  Los demás se omiten.  
  
 Independientemente del escenario, el tiempo de ejecución carga la configuración predeterminada de la federación.  El comportamiento se define como sigue:  
  
1.  Si no hay ningún `<federationConfiguration>` el elemento actual, el tiempo de ejecución crea una configuración de federación y la rellena con los valores predeterminados.  Esta configuración de federación predeterminada hará referencia a la configuración de la identidad predeterminada.  
  
2.  Si un único `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación independientemente de si lo es con nombre o sin nombre.  Si su `identityConfiguration` se especifica el atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
3.  Si un sin nombre `<federationConfiguration>` elemento está presente, es la configuración predeterminada de la federación.  Si su `identityConfiguration` se especifica el atributo, se hace referencia a la configuración de identidad con nombre; de lo contrario, se hace referencia a la configuración de la identidad predeterminada.  
  
4.  Si múltiples denominada `<federationConfiguration>` elementos están presentes y sin nombre no `<federationConfiguration>` elemento está presente, se produce una excepción.  
  
 Normalmente, un sólo `<federationConfiguration>` se define la sección.  En esta sección es la configuración predeterminada de la federación.  Puede especificar múltiples, denominado de forma única `<federationConfiguration>` elementos; Sin embargo, en este caso, si desea cargar una configuración de federación distinto de aquél sin nombre, debe proporcionar un controlador para el.  <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>evento y el conjunto de la <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> propiedad dentro del controlador a un <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> objeto inicializado con los valores de la correspondiente `<federationConfiguration>` elemento en el archivo de configuración.  
  
 El `<federationConfiguration>` elemento está representado por el <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> clase.  El propio objeto de configuración está representado por el <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> clase.  Un único <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> instancia se establece en el <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> propiedad y proporciona configuración federado para la aplicación.  
  
## Ejemplo  
 El XML siguiente se muestra un `<federationConfiguration>` elemento que especifica la configuración de la WSFAM y especifica que el controlador de cookie predeterminado \(una instancia de la <xref:System.IdentityModel.Services.ChunkedCookieHandler> clase\) utilizada por el SAM.  
  
> [!WARNING]
>  domain  Esto es debido a que la `requireHttps` de atributo en el `<wsFederation>` elemento y el `requireSsl` de atributo en el `<cookieHandlerElement>` son `false`.  Esta configuración no se recomienda para la mayoría de los entornos de producción, ya que pueden presentar un riesgo de seguridad.  
  
```  
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
  
## Vea también  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>   
 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)