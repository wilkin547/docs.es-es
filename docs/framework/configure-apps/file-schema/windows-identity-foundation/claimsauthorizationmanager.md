---
title: "&lt;claimsAuthorizationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;claimsAuthorizationManager&gt;
Registra un administrador de autorización de reclamaciones para las notificaciones entrantes.  
  
## Sintaxis  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## Atributos y elementos  
 En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|type|Un tipo personalizado que se deriva de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase.  Para obtener más información acerca de cómo especificar el `type` de atributo, consulte [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### Elementos secundarios  
 Si no hay ningún `type` atributo, o si la `type` las referencias de atributo el <xref:System.Security.Claims.ClaimsAuthenticationManager> \(clase\), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios; Sin embargo, las clases derivadas de <xref:System.Security.Claims.ClaimsAuthorizationManager> puede definir los elementos de configuración secundarios.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|Especifica la configuración de la identidad de nivel de servicio.|  
  
## Comentarios  
 El comportamiento predeterminado proporcionado a través de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase siempre autoriza las notificaciones entrantes.  Si no hay `type` se especifica el atributo o si la `type` especifica el atributo de la <xref:System.Security.Claims.ClaimsAuthorizationManager> \(clase\), el `<claimsAuthorizationManager>` elemento no tiene elementos secundarios.  Puede especificar el `type` atributo para registrar un tipo derivado de la <xref:System.Security.Claims.ClaimsAuthorizationManager> clase para implementar un comportamiento personalizado.  En las próximas secciones se describen los atributos, los elementos secundarios y los elementos primarios.  None  
  
> [!IMPORTANT]
>  Elemento  Descripción  Si la aplicación no es una aplicación Web pasiva, el `<claimsAuthorizationManager>` elemento \(y sus elementos de directiva de secundarios, si está presente\) de la configuración de identidad que se hace referencia son los únicos valores que se aplica.  Todas los demás valores se omiten.  Para obtener más información, vea el elemento [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md).  
  
 Elemento  
  
## Ejemplo  
 Descripción  El código que implementa el Administrador de autorización de reclamaciones capaz de utilizar esta directiva se puede encontrar en el `ClaimsBasedAuthorization` ejemplo.  
  
```  
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