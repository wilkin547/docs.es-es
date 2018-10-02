---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: a745339cffdada56a9b7f27f3f879b9d437c2da2
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032106"
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
Registra un administrador de autorización de notificaciones para las notificaciones entrantes.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthorizationManager >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Un tipo personalizado que deriva la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipos personalizado](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Si no hay ningún `type` atributo, o si el `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> (clase), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> puede definir elementos de configuración secundarios.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica los valores de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Comentarios  
 El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes. Si no hay ningún `type` se especifica el atributo o si la `type` atributo especifica el <xref:System.Security.Claims.ClaimsAuthorizationManager> (clase), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios. Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar un comportamiento personalizado. Las clases derivadas pueden admitir la configuración a través de los elementos secundarios de la `<claimsAuthorizationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> método para controlar estos elementos. El esquema definido para los elementos secundarios es hasta el Diseñador de la clase.  
  
> [!IMPORTANT]
>  Cuando se usa el <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> o <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad al que hace referencia el `<federationConfiguration>` elemento configura el Administrador de autorización de notificaciones y la directiva que se utiliza para realizar decisiones de autorización. Esto es cierto incluso en escenarios que no son escenarios pasivos de Web, por ejemplo, las aplicaciones de Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación Web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos secundarios de directiva, si está presente) de la configuración de identidad que se hace referencia son la única configuración aplicada. Se omiten todas las demás opciones. Para obtener más información, consulte el [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) elemento.  
  
 Este elemento establece el <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente XML muestra la configuración de una autorización de notificaciones de administrador que implementa la directiva formada por pares de recurso-acción cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso. El código que implementa el Administrador de autorización de notificaciones capaz de usar esta directiva puede encontrarse en el `ClaimsBasedAuthorization` ejemplo.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
