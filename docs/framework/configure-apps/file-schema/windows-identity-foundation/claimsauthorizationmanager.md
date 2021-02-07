---
description: 'Más información acerca de: <claimsAuthorizationManager>'
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: ae96c9e665c8533567ad87cad374919c30a6b3c7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664241"
---
# \<claimsAuthorizationManager>

Registra un administrador de autorización de notificaciones para las notificaciones entrantes.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthorizationManager>**  
  
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
|type|Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase. Para obtener más información sobre cómo especificar el `type` atributo, vea [referencias de tipo personalizado](../windows-workflow-foundation/index.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Si no hay ningún `type` atributo, o si el `type` atributo hace referencia a la <xref:System.Security.Claims.ClaimsAuthenticationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios; sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> pueden definir elementos de configuración secundarios.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<identityConfiguration>](identityconfiguration.md)|Especifica la configuración de identidad de nivel de servicio.|  
  
## <a name="remarks"></a>Observaciones  

 El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes. Si no `type` se especifica ningún atributo o si el `type` atributo especifica la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase, el `<claimsAuthorizationManager>` elemento no toma los elementos secundarios. Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar el comportamiento personalizado. Las clases derivadas pueden admitir la configuración a través de elementos secundarios del `<claimsAuthorizationManager>` elemento invalidando el <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> método para controlar estos elementos. El esquema definido para los elementos secundarios es hasta el diseñador de la clase.  
  
> [!IMPORTANT]
> Cuando se usa la <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> clase o para proporcionar control de acceso basado en notificaciones en el código, la configuración de identidad a la que hace referencia el `<federationConfiguration>` elemento configura el administrador de autorización de notificaciones y la Directiva que se usa para tomar decisiones de autorización. Esto es cierto, incluso en escenarios que no son escenarios web pasivos, por ejemplo, aplicaciones Windows Communication Foundation (WCF) o una aplicación que no está basada en Web. Si la aplicación no es una aplicación web pasiva, el `<claimsAuthorizationManager>` elemento (y sus elementos de directiva secundarios, si existen) de la configuración de identidad a la que se hace referencia son los únicos valores aplicados. Todos los demás valores no se tienen en cuenta. Para obtener más información, vea el [\<federationConfiguration>](federationconfiguration.md) elemento.  
  
 Este elemento establece la <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> propiedad.  
  
## <a name="example"></a>Ejemplo  

 En el XML siguiente se muestra la configuración de un administrador de autorización de notificaciones que implementa la Directiva formada por pares de acción-recurso, cada uno de los cuales especifica combinaciones booleanas de las notificaciones que un solicitante debe poseer para realizar la acción en el recurso. El código que implementa el administrador de autorización de notificaciones capaz de usar esta Directiva se puede encontrar en el `ClaimsBasedAuthorization` ejemplo.  
  
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
