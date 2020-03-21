---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152509"
---
# <a name="systemidentitymodelservices"></a>\<system.identityModel.services>
Sección de configuración para la autenticación mediante el protocolo WS-Federation.  
  
[**\<configuración>**](../configuration-element.md)\
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
|[\<federationConfiguration>](federationconfiguration.md)|Contiene los valores <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> que configuran los módulos <xref:System.IdentityModel.Services.SessionAuthenticationModule> HTTP (WSFAM) y (SAM).|  
  
### <a name="parent-elements"></a>Elementos primarios  
 None  
  
## <a name="remarks"></a>Observaciones  
 Agregue `<system.identityModel.services>` una sección al archivo de configuración de la aplicación para proporcionar la configuración de SAM y WSFAM.  
  
> [!IMPORTANT]
> Cuando se <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> usa <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> la clase o la para proporcionar control de<xref:System.Security.Claims.ClaimsAuthorizationManager>acceso basado en notificaciones en el código, el administrador de autorización de notificaciones ( ) y la directiva que se usa para tomar decisiones de autorización se configuran a través de un `<identityConfiguration>` elemento al que se hace referencia implícita o explícitamente desde un `<federationConfiguration>` elemento de esta sección. Para obtener más información, vea el **Comentarios** en el [ \<federationConfiguration>](federationconfiguration.md) elemento.  
  
 La `<system.identityModel.services>` sección está representada <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> por la clase. La colección `<federationConfiguration>` de elementos secundarios configurados <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> en la sección se representa mediante la clase.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra `<system.identityModel.services>` cómo agregar una sección a un archivo de configuración. Primero debe agregar declaraciones de `<system.identityModel.services>` sección `<system.identityModel>` para la sección y las secciones. (Al agregar `<system.identityModel.services>` una sección, también debe agregar `<system.identityModel>` una declaración `<identityConfiguration>` para la sección para asegurarse de que el tiempo de ejecución puede crear una sección predeterminada si es necesario.) Una vez agregadas las declaraciones de sección, puede `<system.identityModel.services>` configurar los valores de autenticación federada en el elemento.  
  
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
