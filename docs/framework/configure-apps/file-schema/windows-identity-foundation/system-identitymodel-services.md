---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: bef061c5c982fb0e740f889336a3b334bc19225e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943660"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Sección de configuración para la autenticación mediante el protocolo WS-Federation.  
  
 \<system.identityModel.services>  
  
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
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<federationConfiguration>](federationconfiguration.md)|Contiene la configuración que configura los <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> módulos http (WSFAM) <xref:System.IdentityModel.Services.SessionAuthenticationModule> y (SAM).|  
  
### <a name="parent-elements"></a>Elementos primarios  
 None  
  
## <a name="remarks"></a>Comentarios  
 Agregue una `<system.identityModel.services>` sección al archivo de configuración de la aplicación para proporcionar la configuración de Sam y WSFAM.  
  
> [!IMPORTANT]
> Cuando se usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> la <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, el administrador de<xref:System.Security.Claims.ClaimsAuthorizationManager>autorización de notificaciones () y la Directiva que se usa para tomar `<identityConfiguration>` decisiones de autorización se configuran mediante un elemento al que se hace referencia de forma implícita o explícita `<federationConfiguration>` desde un elemento de esta sección. Para obtener más información, vea las **notas** en el [ \<elemento > de federationConfiguration](federationconfiguration.md) .  
  
 La sección se representa mediante la <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> clase. `<system.identityModel.services>` La colección de elementos `<federationConfiguration>` secundarios configurada en la sección se representa <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> mediante la clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra cómo agregar una `<system.identityModel.services>` sección a un archivo de configuración. Primero debe agregar declaraciones de sección para la `<system.identityModel.services>` sección y las `<system.identityModel>` secciones. (Al agregar una `<system.identityModel.services>` sección, también debe agregar una declaración para la `<system.identityModel>` sección para asegurarse de que el tiempo de `<identityConfiguration>` ejecución puede crear una sección predeterminada, si es necesario). Una vez agregadas las declaraciones de sección, puede configurar las opciones de autenticación federada en `<system.identityModel.services>` el elemento.  
  
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
